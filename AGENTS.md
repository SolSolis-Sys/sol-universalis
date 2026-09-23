# Sol Universalis — Définition des Agents

Pipeline multi-agents pour la production de vidéos pédagogiques animées style « Il était une fois… ».

## Architecture technique retenue (Option B)

| Couche              | Outil              | Rôle                                      |
|---------------------|--------------------|-------------------------------------------|
| Image brute / Skin  | **Python**         | Génération déterministe 16:9 des personnages |
| Animation           | **Manim**          | Clips animés (morphs, transformations, caméra) |
| Montage final       | **React / Remotion** | Assemblage des clips + audio + timing + export |

## Ordre d’exécution strict

1. **Rédacteur en Chef** (`agents/redacteur_en_chef.md`)  
   Structure le projet, distribue, valide chaque étape.

2. **Scripteur** (`agents/scripteur.md`)  
   Produit `script.json` (voix-off + timings ≥ 61 s).

3. **Storyboarder** (`agents/storyboarder.md`)  
   Produit `storyboard.json` + descriptions d’images 16:9.

4. **Technicien Python** (`agents/technicien_python.md`)  
   - Génère skins 16:9 (Python déterministe)  
   - Génère TTS Maestro  
   - Produit les factories Manim + rend les clips animés Manim

5. **Monteur** (`agents/monteur.md`)  
   Assemble les clips Manim + audio dans **Remotion** → `video_finale.mp4`

## Règles transversales
- Durée finale obligatoire : **61–75 secondes**
- Toutes les images de référence : **16:9 (1280×720)**
- Personnages → skins Python + factories Manim
- Pure narration visuelle (pas de slides / sous-titres)
- Continuité stricte via `assets_design/personnages/`

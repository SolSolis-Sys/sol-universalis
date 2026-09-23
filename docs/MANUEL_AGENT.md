# Manuel Agent – Sol Universalis

Document destiné à tout agent (humain ou IA) qui reprend le projet.

## Objectif du système
Produire des vidéos pédagogiques animées de 61–75 secondes dans le style « Il était une fois… », avec :
- Personnification forte des concepts
- Narrateur Maestro
- Continuité visuelle des personnages
- Pure narration visuelle + voix-off

## Architecture officielle
**Python (skins + TTS) → Manim (clips animés) → Remotion (montage final)**

## Ordre d’exécution obligatoire
1. Rédacteur en Chef
2. Scripteur → `script.json`
3. Storyboarder → `storyboard.json`
4. Technicien Python → skins + TTS + clips Manim
5. Monteur (Remotion) → `video_finale.mp4`

Ne jamais sauter d’étape de validation.

## Fichiers critiques à lire en premier
- `README.md`
- `AGENTS.md`
- `TODO.md`
- `agents/*.md`
- `assets_design/personnages/*.md`
- `scripts/saison-00/episode-00/script.json`

## Outils à privilégier
Toujours utiliser les scripts du dossier `outils/` plutôt que de réécrire la logique :
- `tts_maestro.py`
- `check_duration.py`
- `image_gen/generate_character.py`

## Règles de qualité
- Durée finale ≥ 61 s (vérifier avec `check_duration.py`)
- Format vidéo 1280×720
- Pas de texte/slides à l’écran
- Continuité stricte des personnages

## Boucle d’apprentissage
Après chaque livraison :
1. Noter les problèmes rencontrés
2. Améliorer le générateur Python ou les factories Manim
3. Mettre à jour ce manuel et le `TODO.md` si nécessaire

# Quran Audio API

Cette API fournit des fichiers audio du Coran récités par Al Hussary.

## Comment utiliser

1. Obtenez les informations sur les sources audio disponibles :
   ```
   GET /data/audio-sources.json
   ```

2. Construisez les URLs pour accéder aux fichiers audio :
   ```
   GET /audio/hussary/{surah_number}/{filename}
   ```

## Exemple d'utilisation dans une application JavaScript

```javascript
// Récupérer les informations sur les sources audio
fetch('https://REMPLACEZ_PAR_VOTRE_NOM_UTILISATEUR_GITHUB.github.io/quran-audio/data/audio-sources.json')
  .then(response => response.json())
  .then(data => {
    const hussaryBaseUrl = data.hussary.baseUrl;
    
    // Construire l'URL pour la sourate Al-Fatiha
    const surahNumber = '001';
    const audioUrl = `${hussaryBaseUrl}/${surahNumber}/001_Al-Fatiha.mp3`;
    
    // Utiliser l'URL dans un élément audio
    const audio = new Audio(audioUrl);
    audio.play();
  });
```

## Licence

Ce projet est sous licence MIT.

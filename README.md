# text_to_speech_api

A simple wrapper for Google's [Text-To-Spech API](https://cloud.google.com/text-to-speech). Simply list the available voices and convert your text to a mp3 by providing your API key, language code and voicename.

## Usage

- add the package as a dependency to your `pubspec.yaml` file:

```yaml
dependencies:
  flutter:
    sdk: flutter
  text_to_speeech_api: ^0.0.1
```

- Initialize the TextToSpeechService (optional: provide your api key)

```dart
TextToSpeechService service = TextToSpeechService('sample api key');
```

- List the available voices (no api key required)

```dart
await service.availableVoices();
```

- Convert your text to a File object (api key required)

```dart
File mp3 = await service.textToSpeech(
  text: 'Hello World',
  voiceName: 'de-DE-Wavenet-D',
  audioEncoding: 'MP3',
  languageCode: 'de-DE'
);
```

- Utilizing [this audioplayer plugin](https://pub.dartlang.org/packages/audioplayer) you could now play your mp3 file :)

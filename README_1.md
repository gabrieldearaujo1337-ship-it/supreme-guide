# VOX V2 - J.A.R.V.I.S. Voice + Perspicácia + Evolutivo

## O que mudou da V1 travada:
V1 = if hora == 6 fala X (despertador bonitinho)
V2 = Cérebro evolutivo que entende contexto

## VOZ CUSTOMIZÁVEL - Agora é J.A.R.V.I.S. de verdade

Problema V1: voz feminina padrão do Android, fria, 1.0x

Solução V2:
- Pitch 0.75 (grave, masculino)
- Rate 0.88 (lento, elegante)
- Busca voz masculina pt-BR no sistema (pt-br-x-male)
- 3 presets no vox_brain.json:
  * jarvis_deep: 0.75 pitch, 0.88 rate (RECOMENDADO - grave Stark)
  * jarvis_british: com sotaque britânico se disponível
  * jarvis_warm: mais humano

Para voz 100% J.A.R.V.I.S. (idêntica filme), integre ElevenLabs:
1. Crie conta em elevenlabs.io
2. Use voz "Adam" ou clone Paul Bettany
3. No VoxService, troque tts.speak() por chamada API ElevenLabs

Código ElevenLabs (descomente):
```
val apiKey = "SUA_KEY"
val audio = ElevenLabsTTS.synthesize(text, voiceId="pNInz6obpgDQGcFmaJgB")
playAudio(audio)
```

## PERSPICÁCIA - não é mais keyword

Antes: if "chover" -> "vai chover 23C"
Agora:
- Guarda últimas 20 frases
- Detecta: intenção + horário + rotina + padrão
- Exemplo: "vai chover" às 22h + rotina 6h trabalho = "Quer ajustar alarme para 5:45?"

## EVOLUTIVO - não fica travado

- vox_brain.json é editável sem recompilar
- Fale "VOX, cria rotina 18h academia" -> salva no brain
- Fale "VOX, sua voz está fria" -> ele baixa pitch automaticamente
- Feedback "VOX, isso foi inútil" -> aprende

## Como testar voz J.A.R.V.I.S.:

1. Instale APK V2
2. Vá em Configurações do Android > Idioma > Texto para voz > Instale pacote pt-BR masculino + en-GB
3. Abra VOX > Diga "Testar voz J.A.R.V.I.S."
4. Deve falar grave, lento, com pausas: "Bom dia... senhor Gabriel..."

Se ainda estiver feminina: Configurações > Acessibilidade > Texto para voz > Motor preferido = Google TTS > Engrenagem > Voz pt-BR > Selecione voz masculina.

## Instalação:
Mesmo processo V1, mas agora com assets/vox_brain.json editável.

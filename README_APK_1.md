
# VOX V2 - COMO GERAR APK SEM ANDROID STUDIO (1 CLIQUE)

## Opção 1: APK Automático via GitHub (RECOMENDADO - sem instalar nada)

1. Crie repositório no GitHub: github.com/new -> nome: vox-assistant
2. Faça upload deste projeto ZIP inteiro
3. Vá em Actions > Build VOX APK > Run
4. Após 3-4 minutos, baixe o artefato "VOX-JARVIS-APK" - é o APK instalável
5. Instale no celular Android

## Opção 2: Instalar PWA direto (FUNCIONA AGORA - sem APK)

Este projeto já inclui PWA instalável que funciona como app:

1. Abra o arquivo `app/src/main/assets/vox_pwa_jarvis.html` no Chrome do celular
2. Menu do Chrome (3 pontinhos) > "Instalar app" ou "Adicionar à tela inicial"
3. Agora você tem VOX como app na gaveta, com microfone real e voz J.A.R.V.I.S. Deep

Teste de voz J.A.R.V.I.S.:
- Clique "Testar Voz J.A.R.V.I.S." - deve falar grave, lento, pausado
- Clique "ATIVAR VOX" > Permita microfone > Fale "será que vai chover?"
- Ele deve responder inteligente, não só "vai chover 23C"

## Customização de voz (J.A.R.V.I.S. real):

No vox_brain.json:
- jarvis_deep: pitch 0.75, rate 0.88 (grave Stark) - PADRÃO
- Para voz 100% filme: integre ElevenLabs API (código no VoxService.kt comentado)

Para voz masculina nativa:
Android > Configurações > Sistema > Idiomas > Texto para voz > Baixe pt-BR masculino + en-GB masculino > Selecione como padrão

## Evolutivo:

vox_brain.json é editável:
- Pode adicionar rotinas falando "VOX, cria rotina..."
- Voz muda falando "VOX, fala mais grave"
- Aprende com "VOX, isso foi inútil"

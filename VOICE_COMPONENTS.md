# Componentes de voz aislados

`voice-components` fija el repositorio privado [capri-voice-packs](https://github.com/emmanuelquintana/capri-voice-packs) como submódulo. Contiene Qwen C++/GGML, Chatterbox Turbo, perfiles autorizados para este proyecto privado, pruebas y Capri Updates Studio para convertir guiones en WAV.

Esta rama añade únicamente el enlace y este documento. No cambia instaladores, workflow ni las fuentes privadas de Capri Desktop. La compilación actual no utiliza el submódulo; los recursos vocales permanecen privados y requieren acceso autorizado.

```powershell
git submodule update --init voice-components
cd voice-components
python scripts/verify_sources.py
```

Para preparar el estudio Windows, seguir `voice-components/docs/UPDATES_STUDIO.md`. Los modelos grandes están en releases del repositorio central con hashes. Qwen comparte modelos/perfiles con Android; Turbo conserva su LoRA inglés y necesita el entorno Python específico. No transferir ese LoRA a Qwen ni al modelo Multilingual.

Claude debe empezar por `voice-components/docs/CLAUDE_INTEGRATION.md`, luego `PC_HANDOFF.md` y `CATALOG_AND_CLIENTS.md`. El handoff ubica los puntos reales del bridge Tauri/Rust y describe PCM, cancelación, liberación y futuras descargas opcionales. No introducir un token personal compartido en instaladores.

**Fidelidad sin aprobar:** el usuario rechazó las pruebas latinas, incluso el ensayo con la frase indicada del video. Consultar `FIDELITY_STATUS.md`; estos perfiles son material de evaluación. Windows Qwen mostró picos RSS de 803–886 MB en frases cortas y unos 86 MB entre respuestas. Turbo consume más memoria y permanece como alternativa PC/inglés.

Validación: fuentes/hashes, síntesis real Windows, cancelación, pruebas Python y navegador documentadas en `voice-components/docs/VALIDATION.md`. No se compiló Tauri ni macOS/Linux en esta entrega.

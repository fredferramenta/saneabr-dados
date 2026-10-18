# saneabr-dados

Base de dados pública usada pelo app **SaneaBR** (iOS) para receber novas edições sem precisar de uma nova versão na App Store.

- `manifest.json` — versão da base (`dados_versao`), endereço do arquivo e versão mínima do app.
- `municipios.json` — indicadores por município (schema 2), gerado por `pipeline/build_data.py`.

**Fontes:** SINISA 2024 (Ministério das Cidades), IBGE (Censo 2022, malha municipal), série histórica SNIS/SINISA.

## Como publicar uma base nova

1. Gere o `municipios.json` com o pipeline e confira o `qa_report.md`.
2. Substitua o arquivo aqui.
3. Aumente `dados_versao` no `manifest.json` (ex.: `2025.1`). O app compara numericamente e baixa na próxima abertura; a nova base passa a valer depois de validada (mais de 5.000 municípios decodificados).

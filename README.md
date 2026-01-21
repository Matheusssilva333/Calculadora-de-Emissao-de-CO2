# Calculadora de Emissões de CO2
Este projeto teve como objetivo desenvolver uma calculadora de emissões de CO2 com o auxilio do Github Copilot para treinar as minhas habilidades.

Estrutura:
- backend/: API Node.js + Express
- frontend/: SPA simples em HTML/JS que consome a API

Como executar (local):
1. Backend
   - cd backend
   - npm install
   - npm start
   - API disponível em http://localhost:3000

2. Frontend
   - cd frontend
   - Serve static files (pode abrir frontend/index.html diretamente no navegador ou usar um servidor estático)
   - Por conveniência, usar `npx http-server . -p 8080` dentro da pasta frontend
   - Acesse http://localhost:8080

API
- POST /api/calc
  - Body JSON:
    {
      "entries": [
        {"type":"car","subtype":"gasoline","amount":120}, 
        {"type":"electricity","subtype":"grid","amount":350}
      ]
    }
  - Resposta:
    {
      "items": [
        {"label":"Carro (gasoline)","amount":120,"factor":0.192,"emission":23.04},
        ...
      ],
      "total": 123.45
    }

Observações
- Os fatores de emissão no projeto são exemplos. Troque pelos fatores oficiais da sua região.
- O backend é modular: adicione novos tipos/subtipos em `backend/utils/emissionFactors.js`.

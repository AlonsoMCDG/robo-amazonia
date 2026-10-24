# Robô da Amazônia

An educational game for learning algorithmic thinking. Players describe in natural language what a robot should do in Amazon-themed missions. Gemma 4 acts as a tutor: it asks questions when instructions are incomplete, translates complete instructions into a restricted set of actions, and explains errors and concepts. The app validates every program and runs it step by step.

## Missions

1. **Reach the exit**: avoid trees on the way.
2. **Put out the fire**: pick up water at the lake, then use it on the fire.
3. **Monitor the checkpoints**: visit every checkpoint, using repetition.

## How to run

1. Download `index.html`.
2. Serve the folder locally (for example, `python3 -m http.server 8000`) and open `http://localhost:8000` in Chrome.
3. Get a free API key at https://aistudio.google.com/apikey.
4. Paste the key in the **"Chave da API"** field on the page and click **Salvar**. The key is stored only in your browser.

The app calls the model `gemma-4-26b-a4b-it` through the Gemini API.

## Security note

This version calls the Gemini API directly from the browser, so the key must not be committed to the repository. The code includes an `API_KEY` constant that is intentionally empty. A future version should move the API call to a backend server, so the key is never exposed to the browser.

## Offline mode

If the API is unavailable, use the **Modo manual (sem IA)** section and paste a JSON program. Example for mission 1:

```json
[{"acao":"mover","direcao":"baixo","passos":1},{"acao":"mover","direcao":"direita","passos":9},{"acao":"mover","direcao":"cima","passos":1}]
```

## Built with

HTML5 Canvas, vanilla JavaScript, Web Speech API (voice input, Chrome), Gemma 4 via the Gemini API.

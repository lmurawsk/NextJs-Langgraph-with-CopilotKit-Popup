# Intro

[CopilotKit](https://docs.copilotkit.ai/) to framework m.in do szybkiej integracji agentów zbudowanych w LangGraph z frontendem.

https://docs.copilotkit.ai/coagents

Ten przykład pochodzi dokładnie stąd: https://github.com/CopilotKit/CopilotKit/tree/main/examples/langgraph-tutorial-quickstart

Jest to testowy projekt pochodząc 
https://docs.copilotkit.ai/coagents/quickstart/langgraph

##################################################################

Projekt składa się z dwóch modułów.  
1. `agent-py` - backend. Jest tam plik agenta napisany w langgraph `agent.py` oraz wrapper w fastapi. Więc to nie jest tak, ze CopilotKit pozwala korzystać z lokalnego serwera langchain. Piszą, ze niby mogę tak zrobic gdy zrobię deployment na Langchain Cloud ale jeszcze nie testowałem. Trzeb
2. `ui` - frontend w Nextjs

##################################################################
# Setup od zera

## Ad.1. agent-py

Python package manager dla agentów - poetry:  
1. Konfiguracja srodowiska uruchomieniowego python uzywając poetry:
- `pipx install poetry` (tylko raz per system)
- `cd agent-py/tutorial_quickstart`
- `poetry install` (instaluje zaleznosci z pyproject.toml ktore instaluje w tymczasowym srodowisku)
- [opcjonalne] sprawdzenie środowiska: `poetry env list`
- po zmianie zaleznosci w pyproject.toml: regeneracja locków `poetry lock` i ponownie `poetry install`

2. Uruchomienie agenta i wystawienie za pomoca fastapi:
- `poetry run demo` - wykonuje komendę `demo` zdefiniowaną w pyproject.toml w sekscji `[tool.poetry.scripts]`

3. Zatrzymanie serwera flask:
- Ctrl+C

## Ad.2. `ui`

- This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).
- `cd ui`
- `pnpm install` - instalacja modułów Node.js
- `pnpm dev` - uruchomienie serwera developerskiego Node.js z frontendem (tutaj za kazdym odswiezeniem widac, ze moduly sie kompilują)
- [opcjonalny produkcyjny build] `pnpm build` - nie działa. gdy wykonuję dostają jakieś błędy, ktorych nie bede teraz debugował.

W przypadku problmeów z zaleznosciami:

- `rm -rf node_modules` - zeby zaczac od zera, na wszelki wypadek usunmy istniejace dependencies
- `pnpm next cache clear` w przypadku problmeów, czasem warto wyczyścić cache
- `pnpm install`
Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

#######################################

# Development

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.

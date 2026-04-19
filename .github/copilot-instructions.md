# Copilot Workspace Instructions

## Mandatory Development Checklist

- Run `dotnet format --verify-no-changes` when formatting or lint-sensitive changes are made.
- Run `dotnet build SocOps/SocOps.csproj` before finishing.
- Run `dotnet test` when tests exist or when a task adds test projects.

## Project Scope

This repo contains `SocOps/`, a .NET 10 Blazor WebAssembly social bingo app. Treat `.solutions/` as workshop reference snapshots unless a task explicitly targets them.

## Architecture

- Put UI and event wiring in `SocOps/Components/`.
- Keep app state, localStorage persistence, and change notifications in `SocOps/Services/BingoGameService.cs`.
- Keep reusable game rules in `SocOps/Services/BingoLogicService.cs`.
- Keep data shapes in `SocOps/Models/` and bingo prompt content in `SocOps/Data/Questions.cs`.

## Working Rules

- Prefer small, focused changes that preserve the existing start -> playing -> bingo flow.
- Use dependency injection, component parameters, and `EventCallback` consistently with the existing Blazor code.
- Reuse the custom utility classes in `SocOps/wwwroot/css/app.css` before adding new CSS.
- If new utilities are necessary, add them in the existing naming style inside `SocOps/wwwroot/css/app.css`.
- Keep persistence logic out of Razor components.
- Avoid editing `bin/`, `obj/`, workshop content, or docs unless the task explicitly calls for it.

## Run Commands

Use `dotnet build SocOps/SocOps.csproj` to validate and `dotnet run --project SocOps/SocOps.csproj` to launch the app locally.

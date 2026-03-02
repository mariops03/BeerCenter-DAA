# DAA Beer Center

iOS app for managing craft beer catalogs. Browse breweries, explore their beers, mark favorites, and keep track of your collection. Built with SwiftUI as a university project for the Advanced Application Development (DAA) course.

## Features

- **Brewery management**: Add, view, and delete breweries, organized by origin (national vs. imported). Each brewery has a name, origin type, and logo.
- **Beer catalog**: Each brewery contains its own beer list. Add beers with name, type (Lager, Amber, IPA...), description, ABV, calories, and a logo (via URL or photo gallery).
- **Favorites**: Mark beers as favorites — they appear in a dedicated section at the top of each brewery's list.
- **Search & sort**: Filter beers by name with a search bar. Sort by name, ABV, type, or calories in ascending/descending order.
- **Beer detail view**: Full beer profile with image, type, description, ABV, and calorie info. Favorited beers show a heart indicator.
- **Swipe actions**: Swipe left on any beer to delete, edit, or toggle favorite. Swipe left on a brewery to delete it.
- **Image handling**: Logos can be loaded from a URL or uploaded from the device's photo gallery (stored as compressed base64).

## Architecture

The app follows the **MVVM pattern**:

```
BeerCenterDAA/
├── BeerCenterDAAApp.swift        # App entry point
├── Modelo.swift                  # Data models (Fabricante, Cerveza)
├── APIService.swift              # REST API client (GET, POST, PUT, DELETE)
├── BeerCenterViewModel.swift     # Business logic and state management
├── Extensiones.swift             # URL validation and image helpers
├── ListaFabricantesView.swift    # Brewery list (main screen)
├── ListaCervezasView.swift       # Beer list per brewery
├── DetallesCervezaView.swift     # Beer detail view
├── AñadirFabricanteView.swift    # Add brewery form
├── AñadirCervezaView.swift       # Add beer form
└── ModificarCervezaView.swift    # Edit beer form
```

Data persistence is handled through a **REST API** backend — all CRUD operations (breweries and beers) go through `APIService.swift`, which communicates with the API via standard HTTP methods.

## Tech stack

- **Swift** / **SwiftUI**
- **MVVM** architecture
- **REST API** integration (URLSession)
- **AsyncImage** for remote image loading
- **PhotosPicker** for gallery image upload
- Xcode / iOS 16.4+

## Demo

A video demo of the app is included in the repo: `APP_TESTING.mp4`

## Context

Built for the **Desarrollo de Aplicaciones Avanzadas (DAA)** course (Computer Engineering degree, Universidad de Salamanca).
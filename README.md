# MySports

A Kotlin Android app demonstrating bottom navigation with a Jetpack Navigation graph.

## Navigation structure

Three top-level destinations are attached to a `BottomNavigationView`:

| Destination | Fragment | Purpose |
| --- | --- | --- |
| **My Sports** (start) | `MySportsFragment` | Primary destination. Cards link to individual sport screens through explicit actions in `res/navigation/mobile_navigation.xml`. |
| Discover | `DiscoverFragment` | Searchable/filterable catalog of all sports; also links to the sport screens. |
| Profile | `ProfileFragment` | Shows followed sports and opens their detail screens through global actions. |

Secondary destinations — `FootballFragment`, `BasketballFragment`, `TennisFragment`, and `BaseballFragment` — are all separate nodes in the same graph. They share `SportDetailFragment`, which reads a `sportKey` graph argument and renders the matching entry from `SportsCatalog`.

## Design

The app uses a soft **baby pink** palette: a light pink app background and card container,
a deeper rose primary for buttons/navigation selection, and pink-toned hero banners for
each sport detail screen. The home screen welcomes the user, shows the four sports in a
two-column card grid with follow badges, and offers an "Explore sports" button that
navigates to Discover through a graph action.

## Extras

- Slide transitions on every sport action.
- Bottom bar hides on focused sport detail screens.
- `MainViewModel` (activity-scoped) keeps the follow state in sync across destinations.
- Search and category chips filter the Discover list.

## Build

Open the folder in Android Studio and run the `app` configuration, or:

```powershell
.\gradlew.bat :app:assembleDebug
```

Requires Android SDK Platform 37 and Build Tools 36.0.0 (both installed locally).

## Capstone Flutter Dashboard

This is a Flutter implementation of the STI Command **Pulse Dashboard** UI, designed primarily for web/desktop form factors and prepared for future **Supabase** integration.

### Getting started

1. **Install dependencies**

   ```bash
   flutter pub get
   ```

2. **(Optional) Configure Supabase**

   The app is already wired to initialize Supabase in `main.dart` when the URL and anon key are provided using Dart compile-time environment variables:

   ```bash
   flutter run -d chrome --dart-define=SUPABASE_URL=YOUR_URL --dart-define=SUPABASE_ANON_KEY=YOUR_ANON_KEY
   ```

   Or when building a release:

   ```bash
   flutter build web --dart-define=SUPABASE_URL=YOUR_URL --dart-define=SUPABASE_ANON_KEY=YOUR_ANON_KEY
   ```

   Until you set these values, the app runs fully offline with mocked UI data.

3. **Run the dashboard**

   For web (recommended for this layout):

   ```bash
   flutter run -d chrome
   ```

   For desktop (if enabled in your Flutter SDK):

   ```bash
   flutter run -d windows
   ```

### Project structure

- `lib/main.dart` – App entry point, theme, and Supabase initialization hook.
- `lib/ui/dashboard_page.dart` – Main Pulse Dashboard layout and all UI components (sidebar, top bar, summary cards, hotzones, RFID feed).

You can now plug Supabase queries into the summary cards, hotzones, and live RFID feed by replacing the mocked data with calls to `Supabase.instance.client`.


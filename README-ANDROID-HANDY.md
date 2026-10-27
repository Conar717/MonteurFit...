# Monteur Fit – APK ohne PC bauen (nur Android-Handy)

Das Projekt enthält einen GitHub Actions Workflow unter `.github/workflows/build-apk.yml`. Er baut bei Push auf `main` oder manuell eine Debug-APK und stellt sie als Artifact bereit.

## Einrichtung am Handy
1. Melde dich im Chrome-Browser bei https://github.com an (kostenloses Konto).
2. Erstelle ein neues **privates** Repository namens `MonteurFit` und wähle **nicht** „Add a README“.
3. Entpacke `MonteurFitAndroid-Projekt-mit-Cloud-Build.zip` in der Dateien-App.
4. Öffne das neue Repository auf github.com und wähle **Add file → Upload files**. Lade den gesamten Inhalt des Ordners `MonteurFitAndroid` hoch, einschließlich des versteckten Ordners `.github`. Falls der Dateiauswahldialog versteckte Ordner nicht anzeigt, lege die Workflow-Datei in GitHub manuell an:
   - Pfad: `.github/workflows/build-apk.yml`
   - Inhalt: aus der gleichnamigen Datei im ZIP kopieren.
5. Tippe auf **Commit changes**.
6. Öffne den Reiter **Actions**, wähle **Build Monteur Fit APK**, tippe **Run workflow** und bestätige.
7. Warte, bis der Lauf grün ist. Öffne den Lauf und lade unter **Artifacts** `MonteurFit-debug-APK` herunter. Entpacke das Artifact-ZIP; darin liegt `app-debug.apk`.
8. Öffne `app-debug.apk` in „Eigene Dateien“ und installiere sie. Android kann fragen, ob Chrome bzw. die Dateien-App Apps installieren darf.

## Sicherheit und Hinweise
- Bewahre das Repository privat auf, weil es deinen App-Quellcode enthält.
- Der Workflow erstellt eine Debug-APK, die für den persönlichen Test geeignet ist, nicht für eine Play-Store-Veröffentlichung.
- Der Artifact-Download ist ein ZIP; darin befindet sich die APK.
- Der Build benötigt Internetzugang und kann beim ersten Lauf einige Minuten dauern.

Hier ist die Schritt-für-Schritt-Anleitung unter Verwendung von `git rebase`:

1. **Lokales Repository aktualisieren**:
    - Öffne Git Bash.
    - Wechsle in dein lokales Repository:
      ```bash
      cd /pfad/zu/deinem/repository
      ```
    - Stelle sicher, dass du auf dem Branch bist, für den der Pull Request erstellt wurde:
      ```bash
      git checkout dein-branch
      ```

2. **Upstream-Änderungen abrufen**:
    - Hole die neuesten Änderungen vom Remote-Repository:
      ```bash
      git fetch
      ```

3. **Branch auf den neuesten Stand bringen mittels Rebase**:
    - Rebase deinen Feature-Branch auf den Zielbranch (z.B. main oder master):
      ```bash
      git rebase origin/main
      ```
    - Wenn es Konflikte gibt, wird Git dich darauf hinweisen und anhalten, damit du sie beheben kannst.

4. **Konflikte beheben**:
    - Öffne die Dateien mit Konflikten. Git markiert die Konfliktstellen mit:
      ```plaintext
      <<<<<<< HEAD
      (deine Änderungen)
      =======
      (Änderungen aus dem Zielbranch)
      >>>>>>> main
      ```
    - Bearbeite die Dateien manuell und entscheide, welche Änderungen du behalten möchtest. Entferne die Markierungen (`<<<<<<<`, `=======`, `>>>>>>>`).
    - Nachdem du die Konflikte behoben hast, füge die geänderten Dateien zur Staging-Area hinzu:
      ```bash
      git add datei-mit-konflikt
      ```
    - Setze den Rebase-Prozess fort:
      ```bash
      git rebase --continue
      ```
    - Wiederhole diesen Schritt, bis alle Konflikte behoben sind.

5. **Änderungen pushen**:
    - Da ein Rebase die Commit-Historie ändert, musst du einen Force-Push durchführen, um die Änderungen in das Remote-Repository zu übertragen:
      ```bash
      git push --force
      ```

6. **Pull Request abschließen**:
    - Gehe zu Azure DevOps und überprüfe den Pull Request. Stelle sicher, dass alle Änderungen korrekt sind und dass der Pull Request keine weiteren Konflikte hat.
    - Wenn alles in Ordnung ist, kannst du den Pull Request abschließen.

Achtung: Ein Rebase ändert die Commit-Historie und kann zu Problemen führen, wenn andere Entwickler denselben Branch verwenden. Stelle sicher, dass du alle Beteiligten informierst und sicherstellst, dass sie ihre lokalen Kopien aktualisieren.

Falls du noch Fragen hast oder weitere Unterstützung benötigst, lass es mich wissen!
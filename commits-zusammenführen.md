# Git-commits zusammenführen

Um mehrere Commits zu einem Einzelnen zusammen zu führen kann in Git der Befehl `git rebase -i <Commits>` genutzt werden.

Bevor man das tut sollte mit `git status` geprüft werden ob derzeit Änderungen vorliegen. Wenn dem so ist sollte man diese mit `git stash` für die spätere Weiterbearbeitung zwischengespeichert werden.

Mit `git rebase -i HEAD~4` sagen wir nun bescheid, dass wir die letzten 4 Commits für das Rebasing im interaktiven Modus haben möchten.
In der Textdatei die öffnet werden in den ersten vier Zeilen die letzten 4 Commits angezeigt.
Wir picken die erste, in dem wir ein 'pick ' an den Anfang der Zeile packen, bzw. ein evtl. vorhandenes 'pick ' stehen lassen und an die Zeilen die wir dazupacken wollen packen wir ein 's ' für 'stash'.

Wir speichern die Datei und verlassen den Editor. Dann kommen wir in die nächste Datei in der wir die Commit-message für den Commit bearbeiten können, wie gewohnt.

Wenn dieser Vorgang abgeschlossen ist können wir mit `git stash apply` unsere gebunkerten Änderungen wieder ins CWD holen.
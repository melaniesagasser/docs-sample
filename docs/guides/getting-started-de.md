# Erste Schritte mit der User API

Dieses Handbuch erläutert, wie Sie Ihren API-Schlüssel authentifizieren und eine Beispielanfrage an die User API senden.

## Überblick

Mit der User API können Sie Benutzer verwalten. Sie können Benutzer anlegen und eine Liste aller Benutzer abrufen.

## Voraussetzungen

Um die User API zu verwenden, benötigen Sie Folgendes:

1. Ein Entwicklerkonto oder einen Registrierungslink. Weitere Informationen erhalten Sie von Ihrem IONOS-Vertriebspartner.
2. Einen API-Schlüssel, den Sie über das API-Schlüssel-Portal erhalten. Weitere Informationen finden Sie unter [Authentifizierung](#authentifizierung).
3. Ein Tool zum Senden von API-Anfragen, zum Beispiel Postman oder `curl`.

## Authentifizierung

Die User API verwendet API-Schlüssel zur Authentifizierung. Sie müssen Ihren API-Schlüssel einmalig anlegen, um API-Anfragen senden zu können.

Um Ihren API-Schlüssel anzulegen, folgen Sie den Schritten im [IONOS Developer Guide](https://developer.hosting.ionos.de/docs/getstarted).

Speichern Sie unbedingt sowohl das öffentliche Prefix als auch das Secret des Schlüssels, da Sie beides für die API-Anfrage im nächsten Schritt benötigen.

## Erste API-Anfrage senden

In diesem Beispiel legen Sie einen Benutzer im System mithilfe Ihres API-Schlüssels an.

Kopieren Sie das folgende `curl`-Beispiel und ersetzen Sie dabei `publicprefix.secret` mit den Angaben aus Ihrem persönlichen API-Schlüssel, den Sie zuvor im Schritt [Authentifizierung](#authentifizierung) angelegt haben:

````bash
curl -X POST "https://api.hosting.ionos.com/v1/users?id=aschmidt&name=Anna%20Schmidt"  \
  -H "X-API-Key: publicprefix.secret"
````

Fügen Sie das angepasste `curl`-Beispiel in Ihr API-Anfragetool ein. Sie sollten folgende Antwort erhalten:

````json
  {
    "id": "aschmidt",
    "name": "Anna Schmidt"
  }
````

## Ergebnis

Sie haben erfolgreich Ihren ersten Benutzer im System angelegt: Anna Schmidt mit der Benutzer-ID aschmidt.


**Note:** The literal translations avoided:

- "The User API lets you manage users." -> wurde übersetzt mit "Mit der User API können Sie Benutzer verwalten." -> Warum: "Die User API lässt Sie Benutzer verwalten." als wörtliche Übersetzung klingt nicht professionell und umgangssprachlich, und als ob die API so gnädig ist, mich etwas tun zu lassen.
- "A tool for making API requests" -> wurde übersetzt mit "Ein Tool zum Senden von API-Anfragen". -> Warum: "tool" mit "Werkzeug" zu übersetzen ist nicht gebräuchlich und wäre verwirrend. "make" mit "machen" zu übersetzen klingt zu umgangssprachlich, "Senden" ist Fachsprache.

Die Beispiele zeigen, dass man nicht Wort-für-Wort übersetzen kann sondern den Kontext erfassen muss und den Text eventuell umschreiben und anpassen sollte.
---
layout: page
title: Berechtigungen
permalink: "concepts/de/authorization/"
language: de
---

Das OneOffixx Berechtigungskonzeptes verfolgt folgende Ziele: 

* Verringerung des administrativen Aufwandes
* Sicherstellung, dass nur benutzerrelevante Daten auf dem Rechner der User synchronisiert werden
* Einbindung der Fachabteilungen zur Pflege der Inhaltsdaten von Textbausteinen
* Einschränkung der Sichtbarkeit von Vorlagen und Textbausteinen aufgrund der Organisations und Rollenzugehörigkeit
* Unterstützung von Active Directory und Windows Gruppen

Das Berechtigungskonzept von OneOffixx basiert auf Rollen, Benutzer, Benutzergruppen und Objekten. Rollen, und damit Rechte, werden den Objekten durch AD-Gruppen, AD-Benutzer, OneOffixx-Gruppen oder OneOffixx-User verknüpft.

![x]({{ site.baseurl }}/assets/content-images/concepts/de/system-authorization.png "Berechtigung")

OneOffixx-Gruppen und OneOffixx-User sind eigenständige Authorisierungsklassen. Einer OneOffixx Gruppe kann AD Gruppen bzw AD-User oder auch OneOffixx User enthalten.

{:.table .table-striped}
Berechtigung \ Rolle | Sys-Admin | Org-Admin | User-Admin | Template-Admin | Campaign-Admin | Snippet-Admin | Benutzer | 
---------|----------|---------|---------|---------|---------|---------|---------|
Organisationen verwalten | ☑ | ☑ | ☐ | ☐ | ☐ | ☐ | ☐
Logo verwalten | ☑ | ☑ | ☐ | ☐ | ☐ | ☐ | ☐
Vorlagen verwalten | ☑ | ☐ | ☐ | ☑ | ☐ | ☐ | ☐
Vorlagen ändern | ☑ | ☐ | ☐ | ☑_1_ | ☐ | ☐ | ☐
Benutzer verwalten | ☑ | ☐ | ☑ | ☐  | ☐ |☐ | ☐
Globale Textbausteine verwalten | ☑ | ☐ | ☐ | ☑ | ☐ | ☑ | ☑_2_
Vorlagen Textbausteine erstellen | ☑ | ☐ | ☐ | ☑ | ☐ | ☐ | ☐
Private Textbausteine verwalten | ☑ | ☑ | ☑ | ☑ | ☐ | ☑ | ☑
Felder verwalten | ☑ | ☐ | ☐ | ☑ | ☐ | ☐ | ☐
Kampagne verwalten | ☑ | ☐ | ☐ | ☐  | ☑ | ☐ | ☐
Signaturen verwalten | ☑ | ☐ | ☐ | ☑  | ☐ | ☐ | ☐

1. Sofern der Templateadmin das explizite Änderungsecht auf der Vorlage besitzt.
2. Sofern auf dem Textbaustein explizit der User Änderungsrecht besitzt.

Folgende Rollen sind in OneOffixx vorgesehen:

### Rolle OneOffixx-System
Höchste Berechtigung. Mit dieser können die User, AD-Gruppen und OneOffixx-Gruppen aller anderen Administrationsbereiche gesetzt werden und der Zugriff auf’s Web-Backend (bspw. mit der Statistik, Servereinstellungen,…) gewährt werden. 
 
### Rolle OneOffixx-Organisation
Berechtigung für die Modifikation von Organisationseinheiten in OneOffixx (bspw. Logo-Wechsel, Adressänderungen, ….)
 
### Rolle OneOffixx-Useradministration
Berechtigung für die Administration aller User und Profile in OneOffixx (also auch fremde Personen). Das ist für alle diejenigen sinnvoll, die Support für eine OneOffixx Umgebung leisten.
 
### Rolle OneOffixx-Template
Berechtigung, um Vorlagen zu bearbeiten und zu erstellen

### Rolle OneOffixx-Kampagne
Berechtigung, um Kampagnen zu bearbeiten und zu erstellen
 
### Rolle OneOffixx-Snippet
Berechtigung, um Textbausteine auf der Entwicklungs- / Test-Umgebung zu bearbeiten und zu erstellen

### Gruppe pro Abteilung/Amt/Organisation
Eine Gruppe pro Abteilung, damit die Sichtbarkeit der Vorlagen eingeschränkt werden kann, was insbesondere im Bereich der Usability (schnelles Finden der gewünschten Vorlage) hilfreich und sinnvoll ist.




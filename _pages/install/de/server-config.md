---
layout: page
title: OneOffixx Basis Konfiguration
permalink: "install/de/server-config/"
language: de
---

Die Konfiguration umfasst im wesentlichen 3 Schritte und die Admin Webanwendung sollte Sie durch diese Schritte begleiten. Starten können Sie den __"Rampup Guide"__ indem Sie die Admin Seite im Browser aufrufen.

Das Admin-Dashboard hilft bei der Installation bzw. dem Betrieb von OneOffixx, ist aber nur indirekt für den produktiv Betrieb notwendig. 

Die Anleitung bezieht sich auf die OneOffixx Version 3 oder höher. Für Version 2 befindet sich die Anleitung [hier](#version2x).

## Version 3

 {% include new-badge.html version="3" %}
 
__1. Schritt: OneOffixx.config__

Im ersten Schritt wird geprüft ob die __zentrale "OneOffixx.config"__ Datei Konfigurationsparameter enthält. 

Falls nicht, wird direkt der "Rampup Guide" angezeigt. Nehmen Sie die Beispiel-Konfiguration aus dem "Ramup Guide" und
editieren Sie die "OneOffixx.config" Datei manuell oder nutzen Sie den "Config-Editor". 

_OneOffixx.config manuell editieren:_

Die OneOffixx.config befindet sich im OneOffixx Ordner, welcher in der Standardinstallation den Service und weitere Komponenten enthält:

Standard-Ordnerstruktur:

```
    - OneOffixx
        - Admin
	- Hub
	- Service
	- JobHost
	- Web
	- ...
	- OneOffixx.config
``` 

Wichtigster Konfigurationspunkt ist der ConnectionString zur späteren OneOffixx Produktionsdatenbank, welcher wie folgt angegeben werden muss:

    Data Source=localhost;InitialCatalog=oneoffixx;UserID=[user];Password=[PW];MultipleActiveResultSets=True

Für den Fall das die Windows Authentifzierung genutzt wird, sähe der ConnectionString so aus:

    Data Source=localhost;InitialCatalog=oneoffixx;Integrated Security=true;MultipleActiveResultSets=True

__2. Schritt: Datasource Management__
	
Wenn Sie die Konfiguration in der "OneOffixx.config" gespeichert haben (entweder manuell oder per Config-Editor), sollten Sie die Startseite der Admin Webanwendung aufrufen. Sie sollten jetzt einen Eintrag
sehen und können zum "Datasource Management" wechseln.

Falls der SQL User __"dbcreator" Rechte__ besitzt und Sie noch __keine Datenbank__ angelegt
haben drücken Sie auf __"Init"__. 

Dies wird die Datenbank samt den Tabellen anlegen. 

Falls Sie __bereits eine leere Datenbank__ angelegt haben, __markieren Sie die Checkbox__. 

Danach sollte in beiden Fällen die Datenbank erstellt wurden sein.

__3. Schritt: Admin absichern__

Die Server-Komponenten sind nun erfolgreich installiert und konfiguriert. Es empfiehlt sich den Anweisungen des Konfiguration-Wizard zu folgen und den OneOffixx Admin über die "web.config" nur für bestimmte Nutzer freizuschalten. Im "Rampup Guide" sollten Sie einige Beispiele dazu finden.

__4. Schritt: SyncSources konfigurieren__

Eine Übersicht und einige Beispiele dazu finden Sie [hier]({{ site.baseurl }}/install/de/sync-overview). 

__Optional: AddressService konfigurieren__

{% include new-badge.html version="3.3" %}

Adressdaten wurden bislang nur über Client-Seitige Provider bezogen. In der neuen Version gibt es eine Server-Seitige Variante. Mehr Informationen dazu befinden sich [hier]({{ site.baseurl }}/docfunc/de/df/ap/addressservice). 


## Version 2 {% include anchor.html name="version2x" %}

__1. Schritt: OneOffixxAdmin.config__

Im ersten Schritt wird geprüft ob die "OneOffixxAdmin.config" Datei Konfigurationsparameter enthält. 

Falls nicht, wird direkt der "Rampup Guide" angezeigt. Nehmen Sie die Beispiel-Konfiguration aus dem "Ramup Guide" und
editieren Sie die "OneOffixxAdmin.config" Datei manuell oder nutzen Sie den "Config-Editor". 

_OneOffixxAdmin.config manuell editieren:_

Die OneOffixxAdmin.config befindet sich im Admin-Ordner Ihrer OneOffixx Installation.

Wichtigster Konfigurationspunkt ist der ConnectionString zur späteren OneOffixx Produktionsdatenbank, welcher wie folgt angegeben werden muss:

    Data Source=localhost;InitialCatalog=oneoffixx;UserID=[user];Password=[PW];MultipleActiveResultSets=True;Connection Timeout=30

Die Option *MultipleActiveResultSets=True* ist zwingend erforderlich. Die Angabe des *Connection Timeout=30* ist optional und entspricht dem Standard Timeout. Der Wert kann erhöht werden, falls Timeout Probleme auftreten. Es wird allerdings empfohlen die Standardeinstellung beizubehalten und den OneOffixx Support zu kontaktieren falls das Problem auftritt.

Für den Fall das die __Windows Authentifzierung__ genutzt wird, sähe der ConnectionString so aus:

    Data Source=localhost;InitialCatalog=oneoffixx;Integrated Security=true;MultipleActiveResultSets=True;Connection Timeout=30

Hinweis:
In diesem Fall muss der Application Pool des IIS manuell auf den entsprechenden Domain User gesetzt werden. 
Zusätzlich empfiehlt es sich diesen Domain User in die Gruppe 'IIS_IUSRS' aufzunehmen.

__2. Schritt: Datasource Management__
	
Wenn Sie die Konfiguration in der "OneOffixxAdmin.config" gespeichert haben (entweder manuell oder per Config-Editor), sollten Sie die Startseite der Admin Webanwendung aufrufen. Sie sollten jetzt einen Eintrag
sehen und können zum "Datasource Management" wechseln.

Falls der SQL User __"dbcreator" Rechte__ besitzt und Sie noch __keine Datenbank__ angelegt
haben drücken Sie auf __"Init"__. 

Dies wird die Datenbank samt den Tabellen anlegen. 

Falls Sie __bereits eine leere Datenbank__ angelegt haben, __markieren Sie die Checkbox__. 

Danach sollte in beiden Fällen die Datenbank erstellt wurden sein.

__3. Schritt: OneOffixx.config__

Im letzten Schritt müssen Sie die eigentlichen OneOffixx Anwendungen, d.h. die Service, Connect oder Web-Anwendung, mit den darin enthaltenen "OneOffixx.config" Dateien konfigurieren. Geben Sie hier den
ConnectionString von der OneOffixx Produktionsdatenbank an.

__Admin absichern__

Die Server-Komponenten sind nun erfolgreich installiert und konfiguriert. Es empfiehlt sich den Anweisungen des Konfiguration-Wizard zu folgen und den OneOffixx Admin über die "web.config" nur für bestimmte Nutzer freizuschalten. Im "Rampup Guide" sollten Sie einige Beispiele dazu finden.

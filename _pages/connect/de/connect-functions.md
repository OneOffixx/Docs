---
layout: page
title: Connect Functions
permalink: "connect/de/connect-functions/"
subtitle: "//OneOffixxConnectBatch/Entries/OneOffixxConnect/Function"
language: de
---

Über das __"Function"__-Element können Daten und Steuerinformationen den definierten Dokumentfunktionen übergeben werden. Das Function-Element hat bei jeder Dokumentfunktion den gleichen Aufbau, lediglich die "Arguments" und "Settings" sind jeweils verschieden. 

Über die __"id"__ wird die aufzurufende Dokumentfunktion definiert. Das Attribut "name" ist optional, ist aber für die Lesbarkeit hilfreich.

	<Function id="x" name="Dokumentfunktion Beispiel">
		<Arguments>...</Arguments>
		<Settings>...</Settings>
	</Function>
 
{% include alert.html type="warning" text="Im OneOffixx muss die aufzurufende Dokumentfunktion in der jeweiligen Vorlage auch definiert sein." %}
 
## Dokumentfunktionen 

{:.table .table-striped}
| Id  | Name | Beschreibung |                      
| --- | ---- | --- |
| 70E94788-CE84-4460-9698-5663878A295B | [CustomInterfaceConnector]({{ site.baseurl }}/connect/de/functions/custominterface/) | Daten aus einer Fachapplikation übergeben |
| 6f6430fe-6c11-41de-9f29-c29fef4de861 | [CustomXmlPartsInjector]({{ site.baseurl }}/connect/de/functions/customxml/) | Fachapplikationsspezifische CustomXML Parts übernehmen |
| 5c8b5321-e02d-4a1c-80e3-627d40aeabaf | [ProfileData]({{ site.baseurl }}/connect/de/functions/profiledata/) | Profildaten aus Fachapplikation übernehmen |
| 2de8db66-f3d7-456d-bba3-6bb0f12c1fb6 | [DocumentParameter]({{ site.baseurl }}/connect/de/functions/documentparameter/) | Daten im Dokument als Inhalte abbilden |
| b9e8ec94-bec0-418a-b985-c565ac3bec23 | [Recipient]({{ site.baseurl }}/connect/de/functions/recipient/) | Kontaktinformationen als Empfängeradressen hinterlegen |
| dd752747-733e-4175-9fc7-028ab7472742 | [SnippetResolver]({{ site.baseurl }}/connect/de/functions/snippets/) | Textbausteine einbauen |
| c364b495-7176-4ce2-9f7c-e71f302b8096 | [MetaData]({{ site.baseurl}}/connect/de/functions/metadata/) | Daten im Dokument in den Dokumenteigenschaften setzen |
| d96565fd-b4f0-4939-910f-2b4962a235c5 | [nest/ise]({{ site.baseurl}}/connect/de/functions/nestise/) | Anbindung des Produktes "nest/is-e" |

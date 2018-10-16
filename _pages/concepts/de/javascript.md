---
layout: page
title: OneOffixx Javascript
permalink: "concepts/de/javascript"
language: de
---

{% include new-badge.html version="3.3.1" %}
Die neue Javascript-API wird für Mappings und für bedingte Untervorlagen verwendet. Der Dokument-Parameter und das Scripting verwenden diese Definition noch *nicht*. Es wird ES5 JavaScript unterstützt.

## Expressions

Expressions in Bedingungen können jeweils in zwei Formaten definiert werden:

__Expression__

Es kann direkt ein Ausdruck angegeben sein. z. B. `"OO('forname') + ' ' + OO('lastname')"`

__main function__

Existiert eine `function main()` wird diese aufgerufen und der Rückgabewert ausgewertet. So können komplexere Sachverhalte dargestellt werden, wie z.B. das Internationalisieren von schweizer Telefonnummern via einem regulären Ausdruck (Regex) in Javascript:

    function main()
    {
        // normalisiert alle Telefonnummern
        // 0715110500 => +41 71 511 05 00
        // +41 71 511 05 00 => +41 71 511 05 00
        var input = OO('phonenumber').replace(/ /g, '');
        var patt = /((\+|00)41|0)([0-9]+)/;
        var matchArray = patt.exec(input);
        var number = matchArray[3];
        return  "+41 " + number.substring(0,2) + " " + number.substring(2,5)
            + " " + number.substring(5,7)+ " " + number.substring(7,9);
    }

## OO-API-Object

Es steht jeweils ein API-Objekt als `OO` zur verfügung. Dabei kann `OO(identifier)` als Kurzform für `OO.getValue(identifier)` verwendet werden. Wird ein nicht bekannter Schlüssel übergeben, wird `undefined` zurückgegeben.

* __Mappings__ OO gibt jeweils die Quellwerte zurück. Beispielsweise gibt `OO('phone')` im Dateiprovider den Wert in der Spalte `phone` zurück.
* __Untervorlagen__ OO gibt jeweils die Werte im OneOffixx Custom Xml-Part zurück, also z. B. `OO('DocParam.Subject)`.
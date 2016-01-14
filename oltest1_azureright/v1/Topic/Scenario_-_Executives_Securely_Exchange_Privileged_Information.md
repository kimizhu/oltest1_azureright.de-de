---
description: na
keywords: na
title: Scenario - Executives Securely Exchange Privileged Information
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e18cf5df-859e-4028-8d19-39b0842df33d
---
# Szenario – F&#252;hrungskr&#228;fte tauschen vertrauliche Informationen sicher aus
Dieser Abschnitt enthält Anweisungen für Administratoren und einen Leitfaden für Benutzeranweisungen.Sie müssen sich mit den Anweisungen für Administratoren vertraut gemacht haben, ehe Sie Ihre Benutzer über diese Konfiguration informieren.

## Anweisungen für Administratoren
![](../Image/AzRMS_AdminBanner.png)

Befolgen Sie diese Anweisungen, damit Führungskräfte E-Mail-Nachrichten und -Anlagen sicher austauschen können, und Richtlinien automatisch den Zugriff auf die Führungskräfte beschränken, ohne dass sie eine bestimmte Aktion ausführen müssen.Die E-Mail-Nachrichten und -Anlagen werden von Azure Rights Management geschützt.

Die Anweisungen sind unter den folgenden Umständen geeignet:

-   Führungskräfte tauschen vertrauliche Informationen untereinander aus, die für andere nicht freigegeben werden sollen.

-   Führungskräfte können diese E-Mail-Nachrichten quasi wie bisher senden, müssen sie allerdings an eine geschäftliche E-Mail-Adresse anstatt an eine private E-Mail-Adresse senden.

## Anforderungen bei diesem Szenario
Damit die Benutzeranweisungen in diesem Szenario funktionieren, muss Folgendes vorhanden sein:

|Prüfung|Anforderung|Wenn Sie weitere Informationen benötigen|
|-----------|---------------|--------------------------------------------|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Sie haben Konten und Gruppen für Office 365 oder Azure Active Directory vorbereitet:<br /><br />-   Eine E-Mail-aktivierte Gruppe namens **Führungskräfte**<br />-   Alle Führungskräfte sind Mitglieder der Gruppe **Führungskräfte**|[Vorbereiten für Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Ihr Azure Rights Management-Mandantenschlüssel wird von Microsoft verwaltet. Sie verwenden nicht BYOK (Bring your own key, Eigenen Schlüssel verwenden)|[Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](https://technet.microsoft.com/library/dn440580.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Azure Rights Management ist aktiviert.|[Aktivieren von Azure Rights Management](https://technet.microsoft.com/library/jj658941.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Exchange Online ist für Azure Rights Management aktiviert.|Erweitern Sie den Abschnitt [Exchange Online: IRM-Konfiguration](https://technet.microsoft.com/library/jj585031.aspx) unter [Konfigurieren von Anwendungen für Azure Rights Management](https://technet.microsoft.com/library/jj585031.aspx).|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Sie haben wie nachfolgend beschrieben eine benutzerdefinierte Vorlage konfiguriert.|[Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](https://technet.microsoft.com/library/dn642472.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Sie haben wie nachfolgend beschrieben eine Transportschutzregel für IRM konfiguriert .|[Erstellen einer Transportschutzregel](https://technet.microsoft.com/library/dd302432.aspx)|

#### So konfigurieren Sie die benutzerdefinierte Vorlage für E-Mails von Führungskräften:

1.  Im Azure-Portal: Erstellen Sie eine neue benutzerdefinierte Vorlage für Azure Rights Management, die diese Werte und Einstellungen enthält:

    -   Name: **Führungskräfte**

    -   Rechte:  Erteilen Sie der E-Mail-aktivierten Gruppe "Führungskräfte" das Recht **Mitbesitzer**.

2.  Veröffentlichen Sie die neue Vorlage.

3.  Aktualisieren Sie die Vorlagen für Exchange Online mithilfe des Windows PowerShell für Exchange Online-Befehls:

    ```
    Import-RMSTrustedPublishingDomain -Name "RMS Online -1" -RefreshTemplates –RMSOnline
    ```

#### So konfigurieren Sie E-Mail-Nachrichten an und von Führungskräften mit automatischem Schutz:

-   Im Exchange Admin Center: Erstellen Sie eine neue E-Mail-Flussregel, die diese Werte und Einstellungen enthält:

    -   Klicken Sie auf das Symbol "Neu", und wählen Sie **Rechteschutz auf Nachrichten anwenden** aus.

    -   Auf der Seite **Neue Regel**:

        -   Geben Sie einen Namen wie z. B. **Vorlagen vom Typ "Führungskräfte" auf E-Mails von Führungskräften anwenden**.

        -   Für **Regel anwenden, wenn** wählen Sie **Der Absender**...**ein Mitglied dieser Gruppe ist** und dann **Führungskräfte** aus.

        -   Klicken Sie auf **Bedingung hinzufügen**, wählen Sie **Der Empfänger**...**ist Mitglied dieser Gruppe** und dann **Führungskräfte** aus.

        -   Stellen Sie für **Gehen Sie wie folgt vor** sicher, dass **Rechteschutz auf Nachricht anwenden mit** ausgewählt ist. Klicken Sie auf **Bitte auswählen**, um die Vorlage **Führungskräfte** auszuwählen.

        -   Stellen Sie sicher, dass für **Modus für diese Regel auswählen** die Option **Erzwingen** ausgewählt ist.

        -   Klicken Sie auf **Speichern**.

## Benutzeranweisungen
Es gibt keine spezifischen Benutzeranweisungen für dieses Szenario, da der Schutz von E-Mails von und an Führungskräfte keine besondere Aktion von ihnen verlangt.E-Mail-Nachrichten und -Anlagen werden automatisch so geschützt, dass nur die Mitglieder der Gruppe "Führungskräfte" darauf zugreifen können.Allerdings müssen Sie die Führungskräfte und das Helpdesk informieren, dass diese E-Mails automatisch geschützt sind und wie dadurch ihre Nutzung dieser E-Mails eingeschränkt werden kann.Sie können beispielsweise nicht erfolgreich von anderen Personen gelesen werden, wenn die E-Mail-Nachrichten oder -Anlagen später an andere Personen weitergeleitet werden.

Das folgende Beispiel wird möglicherweise als eine Standard-E-Mail-Nachricht an die Führungskräfte gesendet, nachdem Exchange Online für dieses Szenario konfiguriert wurde.

### Beispielbenutzerdokumentation
![](../Image/AzRMS_ExampleBanner.png)

##### IT-Ankündigung: E-Mails von Führungskräften sind jetzt automatisch geschützt.

-   Von nun an werden Inhalte und Anlagen von E-Mail-Nachrichten, die an andere Führungskräfte im Unternehmen gesendet werden, automatisch so geschützt, dass nur andere Führungskräfte im Unternehmen darauf Zugriff haben, um die Informationen zu lesen, zu drucken, zu kopieren usw.Diese Einschränkung gilt auch, wenn Sie die E-Mail-Nachricht an andere weiterleiten oder die Anlagen speichern.Dieser Schutz hilft, Datenverluste bei vertraulichen oder sensiblen Informationen zu vermeiden.

    Wenn Sie möchten, dass Dritte die Informationen in diesen E-Mails lesen und bearbeiten können sollen, müssen Sie sie getrennt per E-Mail an sie senden.

    Wenn Sie vertrauliche Unternehmensinformationen an eine andere Führungskraft senden möchten, wählen Sie deren geschäftliche E-Mail-Adresse und keine private E-Mail-Adresse.

**Benötigen Sie Unterstützung?**

-   Wenden Sie sich an das Helpdesk: helpdesk@vanarsdelltd.com


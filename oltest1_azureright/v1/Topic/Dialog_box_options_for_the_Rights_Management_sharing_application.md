---
description: na
keywords: na
title: Dialog box options for the Rights Management sharing application
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7b91ab30-6363-4929-bcbd-4dfbd05f644a
---
# Dialogfeldoptionen f&#252;r die Rights Management-Freigabeanwendung
Verwenden Sie diese Informationen als Hilfe bei der Angabe der Optionen in den Dialogfeldern **Schutz hinzufügen** oder **Geschützt freigeben** der RMS-Freigabeanwendung. Dieses Dialogfeld wird angezeigt, wenn Sie [eine freizugebende Datei schützen](http://technet.microsoft.com/library/dn574735.aspx) oder [eine Datei auf einem Gerät (direkt) schützen](http://technet.microsoft.com/library/dn574733.aspx) und benutzerdefinierte Berechtigungen auswählen.

> [!IMPORTANT]
> Wenn sich die angezeigten Optionen von den hier dokumentierten unterscheiden, haben Sie wahrscheinlich nicht die neueste Version der Freigabeanwendung installiert. Sie können die neueste Version von der Seite [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) herunterladen.
> 
> Woher wissen Sie, ob Sie die neueste Version verwenden? Suchen Sie in der Liste „Programme und Features“ nach **Microsoft Rights Management-Freigabeanwendung**, und überprüfen Sie die entsprechende Versionsnummer. Damit Sie die Optionen in der Tabelle anzeigen und verwenden können, sollte die verwendete Version mindestens **1.0.1770.0** sein. Sie können die letzte Versionsnummer auf der Downloadseite überprüfen.

Zusätzlich zu den Optionen, die Sie auswählen können, fragen Sie sich vielleicht auch:

-   [Erläuterung zur automatisch erstellten PPDF-Datei](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md#BKMK_PPDF)

-   [Wo liegt der Unterschied zwischen allgemeinem und integriertem (systemeigenem) Schutz?](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md#BKMK_GenericNative)

|Option|Beschreibung|
|----------|----------------|
|**BENUTZER**|Wenn Sie noch keine E-Mail-Adresse aus Outlook angegeben haben, geben Sie die E-Mail-Adressen der Personen ein, die in der Lage sein sollen, die Datei zu öffnen.<br /><br />Wenn in Ihrer Organisation die lokale Version von Rights Management (AD RMS) verwendet wird, sind die E-Mail-Adressen, die Sie angeben können, auf Personen innerhalb Ihrer Organisation beschränkt. Wenn dies zutrifft, und wenn Sie versuchen, externe E-Mail-Adressen anzugeben, wird eine Meldung angezeigt, die besagt, dass Ihre Unternehmenskonfiguration Freigeben von geschützten Inhalten nur innerhalb des Unternehmens zulässt. Wenn in Ihrer Organisation aber Azure RMS verwendet wird, können diese E-Mail-Adressen zu Personen innerhalb Ihrer Organisation oder zu Personen in einer anderen Organisation gehören.<br /><br />Beispiele: janetm@contoso.com, p.dover@fabrikam.com|
|**Allgemeiner Schutz**|Wenn diese Option ausgewählt ist, bedeutet dies, dass die ausgewählte Datei nicht systemeigen geschützt werden kann. Weitere Informationen finden Sie unter [Wo liegt der Unterschied zwischen allgemeinem und integriertem (systemeigenem) Schutz?](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md#BKMK_GenericNative) in diesem Thema.|
|**Anzeigender Benutzer – Nur anzeigen**<br /><br />**Prüfer – Anzeigen und Bearbeiten**<br /><br />**Mitautor – Anzeigen, Bearbeiten, Kopieren und Drucken**<br /><br />**Mitbesitzer – Alle Berechtigungen** **Note:** Jede dieser Optionen hat vor ihrem Namen ein rundes Symbol, das einen Weltglobus darstellt. Dieses Symbol wird verwendet, weil Sie üblicherweise eine dieser Optionen auswählen, wenn Sie eine Anlage an jemanden in einer anderen Organisation senden.|Wählen Sie eine dieser Optionen aus, wenn Sie die Rechte für das geschützte Dokument definieren möchten. Klicken Sie auf jede Option, um eine Beschreibung anzuzeigen.<br /><br />Wenn Sie eine dieser Optionen auswählen, haben nur die Personen, die Sie unter **BENUTZER** angeben, die Rechte, die Sie zum Öffnen und Verwenden des Dokuments angeben. Wenn diese Personen das Dokument beispielsweise an eine andere Person weiterleiten würden, könnte das Dokument nicht geöffnet werden.|
|Richtlinienvorlagen, die von Ihrem Administrator konfiguriert werden.<br /><br />Wenn der Name Ihres Unternehmens beispielsweise Contoso Ltd. lautet: **Contoso Ltd. – Vertraulich** **Note:** Jede dieser Optionen hat vor ihrem Namen ein quadratisches Symbol , das ein Bürogebäude darstellt. Dieses Symbol wird verwendet, weil Sie üblicherweise eine dieser Optionen auswählen, wenn Sie eine Anlage an jemanden in Ihrer Organisation senden.|Beim Freigeben eines Dokuments für Personen, die für Ihre Organisation arbeiten, sehen Sie die verfügbaren Richtlinienvorlagen, die von Ihrem Administrator konfiguriert wurden. Wählen Sie eine dieser Option aus, wenn das Dokument nicht außerhalb Ihrer Organisation freigegeben werden soll.<br /><br />Wenn Sie eine dieser Optionen auswählen, definiert der Administrator sowohl die Rechte für das Dokument als auch, wer es öffnen kann.|
|**Diese Dokumente sollen ablaufen am**|Wählen Sie diese Option nur für zeitkritische Dateien aus, für die es den von Ihnen ausgewählten Benutzern nicht möglich sein soll, sie nach einem von Ihnen angegebenen Datum öffnen zu können. Sie können weiterhin die ursprüngliche Datei öffnen, aber nach Mitternacht (aktuelle Zeitzone) an dem von Ihnen angegebenen Tag können andere Benutzer die Datei nicht öffnen.<br /><br />Diese Option ist nicht verfügbar, wenn Sie eine Richtlinienvorlage auswählen, die der Administrator konfiguriert.|
|**E-Mail an mich, wenn jemand versucht, diese Dokumente zu öffnen**|**Note:** Diese Option ist derzeit als Vorschau verfügbar.<br />Wählen Sie diese Option aus, wenn Sie E-Mail-Benachrichtigungen erhalten möchten, sobald jemand versucht, das Dokument zu öffnen, das Sie schützen. In der E-Mail-Nachricht wird mitgeteilt, wer versucht hat, die Datei zu öffnen, wann dies war ob es erfolgreich war.<br /><br />Diese Option ist nur verfügbar, wenn in Ihrer Organisation Azure RMS verwendet wird. Wenn in Ihrer Organisation die lokale Version von Rights Management (AD RMS) verwendet wird, wird diese Option nicht angezeigt.|
|**Zulassen, dass ich den Zugriff auf diese Dokumente sofort widerrufe**|Wählen Sie diese Option aus, wenn Sie den Zugriff auf die Dokumente später möglicherweise über die Website für die Dokumentnachverfolgung widerrufen müssen und der Widerruf sofort in Kraft treten muss. Ein Auswählen dieser Option bedeutet jedoch, dass Benutzer, solange das Dokument nicht widerrufen ist, bei jedem Zugriff auf das Dokument eine Internetverbindung benötigen, um das Dokument zu lesen. Es gibt möglicherweise einige Szenarios, in denen Benutzer für ihre Geräte keine Verbindung mit dem Internet herstellen können, sodass die Benutzer Ihr Dokument nicht wie von Ihnen beabsichtigt lesen können.<br /><br />Wenn Sie diese Option nicht auswählen, können Sie die Dokumente immer noch später über Website für die Dokumentnachverfolgung widerrufen. Da Benutzer jedoch nicht immer eine Internetverbindung zum Lesen des Dokuments benötigen, erfahren sie nicht sofort, dass das Dokument widerrufen wurde, und können es weiter lesen, bis sie sich das nächste Mal bei Azure RMS authentifizieren. Standardmäßig beträgt die maximale Anzahl von Tagen, an denen jemand ein geschütztes Dokument, das Sie widerrufen haben, weiter lesen kann, 30 Tage, aber ein Administrator kann diesen Wert auf weniger oder mehr als 30 Tage ändern.<br /><br />Diese Option ist nur verfügbar, wenn in Ihrer Organisation Azure RMS verwendet wird. Wenn in Ihrer Organisation die lokale Version von Rights Management (AD RMS) verwendet wird, wird diese Option nicht angezeigt.|

## <a name="BKMK_GenericNative"></a>Wo liegt der Unterschied zwischen allgemeinem und integriertem (systemeigenem) Schutz?

-   Wenn Sie **eine Datei allgemein schützen**, können nicht autorisierte Benutzer die Datei nicht öffnen. Nachdem autorisierte Benutzer die Datei geöffnet haben, könnten diese die Datei jedoch ungeschützt an andere Personen weiterleiten oder sie an einem Ort speichern, auf den andere zugreifen können. Es wird aber eine Meldung angezeigt, die den Benutzern mitteilt, welche Berechtigungen sie für die Datei haben, und sie werden aufgefordert, diese zu akzeptieren. Dieser Schutz kann jedoch nicht erzwungen werden. Außerdem können Sie, wenn Sie eine Datei allgemein schützen, die Berechtigungen nicht weiter einschränken als die Autorisierung. Sie können den Inhalt beispielsweise nicht auf „schreibgeschützt“ oder „nicht druckbar“ einschränken.

    > [!NOTE]
    > Eine allgemein geschützte Datei hat immer die Dateinamenerweiterung **.pfile**.

-   Im Gegensatz dazu gilt bei Verwendung des **integrierten (systemeigenenen) Schutzes** von Rights Management der Schutz für Anwendungen, die diesen unterstützen (z. B. Office-Dateien), auch für die Datei, selbst wenn diese an jemand anderen gesendet oder an einem anderen Ort gespeichert wird. Und wenn Sie diese Dateien schützen, können Sie eingeschränkte Berechtigungen verwenden, z. B. schreibgeschützt oder die Berechtigung zum Bearbeiten, jedoch nicht zum Drucken oder Kopieren. Sie könnten beispielsweise **Anzeigender Benutzer – Nur Anzeigen** auswählen, sodass der Inhalt weder bearbeitet, noch gedruckt oder noch kopiert werden kann.

Weitere technische Informationen finden Sie im Abschnitt [Schutzebenen – systemeigen und generisch](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_LevelsofProtection) im [Rights Management-Freigabeanwendung – Administratorhandbuch](../Topic/Rights_Management_sharing_application_administrator_guide.md).

## <a name="BKMK_PPDF"></a>Erläuterung zur automatisch erstellten PPDF-Datei

-   Wenn Sie eine geschützte Datei per E-Mail freigeben („Geschützt freigeben“), erstellt die RMS-Freigabeanwendung automatisch eine **PPDF**-Version der Datei für Word, Excel, PowerPoint oder PDF. Dies ist eine geschützte schreibgeschützte Version der Datei, die nur autorisierte Personen öffnen können, und es wird sichergestellt, dass die Empfänger die Anlage immer lesen können, selbst wenn sie ein mobiles Gerät verwenden, auf dem es keine Anwendung gibt, die Rights Management unterstützt. Sofern diese Personen die RMS-Freigabe-App installiert haben, können sie die Anlage lesen.

    In diesem Szenario wird, im Gegensatz zu einer allgemein geschützten Datei, die Verwendungseinschränkung erzwungen. Der Empfänger kann diese Version der Datei nicht speichern, und wenn die Anlage an eine andere Person weitergeleitet wird, bleiben die ursprünglichen Einschränkungen für das Dokument erhalten. Nur Personen, die für das geschützte Dokument autorisiert wurden, können dieses öffnen.

    > [!NOTE]
    > Eine PPDF-Datei wird automatisch erstellt, wenn Sie die Option „Geschützt freigeben“ verwenden (Freigabe per e-Mail). Wenn Sie die Option „Direkt schützen“ auswählen, wird dagegen keine PPDF-Datei erstellt.

## Beispiele und weitere Anweisungen
Beispiele für die Verwendung der Rights Management-Freigabeanwendung sowie weitere Anweisungen finden Sie in den folgenden Abschnitten des Benutzerhandbuchs für die Rights Management-Freigabeanwendung

-   [Beispiele für die Nutzung der RMS-Freigabeanwendung](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingExamples)

-   [Was möchten Sie tun?](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingInstructions)

## Siehe auch
[Rights Management-Freigabeanwendung – Benutzerhandbuch](../Topic/Rights_Management_sharing_application_user_guide.md)


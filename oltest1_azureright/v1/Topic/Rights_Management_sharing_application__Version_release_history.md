---
description: na
keywords: na
title: Rights Management sharing application: Version release history
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6751bd90-959f-4eba-91ed-6588ac983762
---
# Rights Management-Freigabeanwendung: Verlauf der Versionsver&#246;ffentlichungen
Das Rights Management-Team aktualisiert die Rights Management-Freigabeanwendung regelmäßig, um Fixes und neue Funktionen zu implementieren. Verwenden Sie die folgenden Informationen, um zu sehen, welche Neuerungen oder Änderungen eine Version bietet. Die neueste Version ist zuerst aufgeführt.

Versionen vor dem 1. Januar 2015 sind nicht aufgeführt.

> [!NOTE]
> Wenn Sie Feedback oder Fragen zur RMS-Freigabeanwendung haben, senden Sie eine E-Mail an [AskIPTeam](mailto:AskIPTeam@microsoft.com?subject=RMS%20sharing%20app:%20Feedback%20or%20question).

## Version 1.0.2004.0
**Veröffentlicht**: 11.12.2015

**Fixes**:

-   Verbesserungen bei Fehlermeldungen (Genauigkeit und Klarheit).

-   Leistungsverbesserungen beim Verschlüsseln und Entschlüsseln von Inhalt.

**Neue Features**:

-   Eine Installation ohne Administratorrechte wird unterstützt, sodass Standardbenutzer die RMS-Freigabeanwendung installieren können.

    Für Standardbenutzer, die Office 2010 verwenden, bestehen einige Einschränkungen. Weitere Informationen finden Sie im Abschnitt [Wenn Sie kein lokaler Administrator sind und Office 2010 verwenden](../Topic/Download_and_install_the_Rights_Management_sharing_application.md#BKMK_SetupOffice2010) der Benutzeranweisungen zum [Herunterladen und Installieren der Rights Management-Freigabeanwendung](../Topic/Download_and_install_the_Rights_Management_sharing_application.md).

## Version 1.0.1908.0
**Veröffentlicht**: 16.9.2015

**Fixes**:

-   Unterstützung für mehrstufige Authentifizierung (MFA) für Azure RMS, wodurch auch die Abhängigkeit vom Microsoft Anmelde-Assistenten für Anwendungen, die eine moderne Authentifizierung verwenden, entfernt wird.

    Weitere Informationen finden Sie im Abschnitt [Multi-Factor-Authentication (MFA) und Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_MFA) in [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md).

## Version 1.0.1784.0
**Veröffentlicht**: 30.7.2015

**Fixes**:

-   Das Standardaktualisierungsintervall für Vorlagen für Benutzerrechterichtlinien wurde von 7 Tagen auf 1 Tag reduziert.

-   Kleine Anzahl von Regressionen und kleinere Fehler.

## Version 1.0.1770.0
**Veröffentlicht**: 25.4.2015

**Fixes**:

-   Nun können nur Besitzer und Mitbesitzer den jeweiligen Schutz entfernen. Mitautoren können den Schutz nicht aufheben.

-   Dateien, die sich auf einer Netzwerkfreigabe befinden, können jetzt geschützt werden.

**Neue Features**:

-   Unterstützung für Dokumentnachverfolgung und -widerruf. Weitere Informationen finden Sie unter [Nachverfolgen und Widerrufen Ihrer Dokumente bei Verwendung der RMS-Freigabeanwendung](../Topic/Track_and_revoke_your_documents_when_you_use_the_RMS_sharing_application.md).

-   Vorlagenunterstützung, wenn Sie **Geschützt freigeben** auswählen:

    -   Sie können nun Vorlagen auswählen.

    -   Statt des Schiebereglers wird ein Listenfeld angezeigt, das Vorlagen und benutzerdefinierte Berechtigungen beinhaltet.

    -   Es werden keine Optionen für **Nutzung auf allen Geräten zulassen** und **Nutzungsbeschränkungen erzwingen** mehr angezeigt. Stattdessen wird je nach Dateityp automatisch **Generischer Schutz** ausgewählt.

    Weitere Informationen finden Sie unter [Dialogfeldoptionen für die Rights Management-Freigabeanwendung](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md).

## Version 1.0.1667.0
**Veröffentlicht**: 19.1.2015

**Fixes**:

-   Unterstützung für chinesische Schriftzeichen im PPDF-Viewer der RMS-Freigabeanwendung.

-   Verbesserte Fehlerbehandlung und -benachrichtigungen.

-   Fix für ein Problem mit der automatischen Updatebenachrichtigung, wenn eine neuere Version der Anwendung zum Download zur Verfügung steht.

**Neue Features**:

-   **Unterstützung für mehrere E-Mail-Domänen innerhalb Ihrer Organisation**: Wenn Sie AD RMS verwenden und Benutzer in Ihrer Organisation über mehrere E-Mail-Domänen verfügen, können die Benutzer durch dieses Update Inhalte verwenden, die von Benutzern in Ihrer Organisation in anderen Domänen geschützt wurden. Weitere Informationen finden Sie im Abschnitt [Nur AD RMS: Unterstützung für mehrere E-Mail-Domänen innerhalb Ihrer Organisation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_FederatedDomains) im [Rights Management-Freigabeanwendung – Administratorhandbuch](../Topic/Rights_Management_sharing_application_administrator_guide.md).


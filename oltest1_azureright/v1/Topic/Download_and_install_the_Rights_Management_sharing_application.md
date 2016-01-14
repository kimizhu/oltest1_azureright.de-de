---
description: na
keywords: na
title: Download and install the Rights Management sharing application
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2bf09690-9dba-43b7-9e0a-0110915d4081
---
# Herunterladen und Installieren der Rights Management-Freigabeanwendung
Sie müssen kein lokaler Administrator sein, um die RMS-Freigabeanwendung zu installieren. Wenn Sie es jedoch nicht sind und Office 2010 verwenden, bestehen einige Einschränkungen. Weitere Informationen finden Sie in diesem Thema im Abschnitt [Wenn Sie kein lokaler Administrator sind und Office 2010 verwenden](#BKMK_SetupOffice2010).

### So laden Sie die Rights Management-Freigabeanwendung herunter und installieren sie

1.  Navigieren Sie zur Seite [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) der Microsoft-Website.

2.  Klicken Sie im Abschnitt **Computer** auf das Symbol für **RMS-App für Windows**, und speichern Sie die Datei **Setup.exe**, um die Microsoft Rights Management-Freigabeanwendung zu installieren.

3.  Doppelklicken Sie auf die heruntergeladene Datei „Setup.exe“. Wenn Sie dazu aufgefordert werden, den Vorgang fortzusetzen, klicken Sie auf **Ja**.

4.  Klicken Sie auf der Seite **Microsoft RMS-Setup** auf **Weiter**, und warten Sie, bis die Installation abgeschlossen wurde.

    > [!NOTE]
    > Die RMS-Freigabeanwendung setzt mindestens Microsoft .NET Framework 4.0 voraus. Beim Setup wird überprüft, ob diese Version installiert ist. Falls nicht, wird eine Nachricht mit einem Link zur Installationsquelle angezeigt.

5.  Am Ende der Installation klicken Sie auf **Neu starten**, um Ihren Computer neu zu starten und die Installation damit abzuschließen. Sie können auch auf **Schließen** klicken, um den Computer später neu zu starten und die Installation abzuschließen.

Damit sind Sie bereit, Ihre Dateien zu schützen und von anderen geschützte Dateien zu lesen.

## <a name="BKMK_SetupOffice2010"></a>Wenn Sie kein lokaler Administrator sind und Office 2010 verwenden
Wenn Sie sich ohne lokale Administratorrechte bei Ihrem Computer anmelden und Setup erkennt, dass Sie Office 2010 installiert ist, werden Sie in einer Warnmeldung darauf hingewiesen, dass einige Szenarien in dieser Konfiguration nicht funktionieren. Dies sind folgende Szenarien:

-   Wenn Ihre Organisation keine lokale Version von RMS, sondern Azure RMS verwendet:

    -   Das Microsoft Office-Feature „Information Rights Management“ (IRM) ist nicht verfügbar. Das betrifft z. B. die Option **Nicht weiterleiten** für E-Mails und die Berechtigungen unter **Zugriff einschränken**, die Sie in Word und Excel im Menü **Datei** festlegen können. Sie können die Option „Geschützt freigeben“ im Menüband verwenden, und Sie können im Datei-Explorer die Kontextmenüoptionen verwenden.

-   Wenn Ihre Organisation nicht Azure RMS, sondern eine lokale Version von RMS verwendet:

    -   Sie können keine geschützten Dokumente lesen, die Sie aus einer anderen Organisation erhalten, in der Azure RMS verwendet wird.

Wenn Sie kein lokaler Administrator sind und Office 365 oder Office 2013 verwenden, wird Ihnen diese Meldung nicht angezeigt, und diese Szenarien werden unterstützt.

Sie können die Installation mit diesen bekannten Einschränkungen fortsetzen. Oder Sie beenden die Installation und führen Sie erneut aus, wählen aber in Schritt 3 beim Ausführen von „Setup.exe“ die Option **Als Administrator ausführen**. Sie können auch einen Administrator bitten, die Installation für Sie auszuführen. Administratoren können [diese Installation per Skript ausführen](https://technet.microsoft.com/library/dn339003.aspx), sodass sie ohne Ihr Zutun automatisch erfolgt.

## Beispiele und weitere Anweisungen
Beispiele für die Verwendung der Rights Management-Freigabeanwendung sowie weitere Anweisungen finden Sie in den folgenden Abschnitten des Benutzerhandbuchs für die Rights Management-Freigabeanwendung

-   [Beispiele für die Nutzung der RMS-Freigabeanwendung](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingExamples)

-   [Was möchten Sie tun?](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingInstructions)

## Siehe auch
[Rights Management-Freigabeanwendung – Benutzerhandbuch](../Topic/Rights_Management_sharing_application_user_guide.md)


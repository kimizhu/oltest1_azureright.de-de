---
description: na
keywords: na
title: Rights Management sharing application administrator guide
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d9992e30-f3d1-48d5-aedc-4e721f7d7c25
---
# Rights Management-Freigabeanwendung – Administratorhandbuch
Verwenden Sie die folgenden Informationen, wenn Sie für die Microsoft Rights Management-Freigabeanwendung in einem Unternehmensnetzwerk verantwortlich sind oder wenn Sie mehr technische Informationen benötigen, als im [Rights Management-Freigabeanwendung – Benutzerhandbuch](../Topic/Rights_Management_sharing_application_user_guide.md) oder in der [FAQ für die Microsoft Rights Management-Freigabeanwendung für Windows](http://go.microsoft.com/fwlink/?LinkId=303971) vorhanden sind:

-   [Automatische Bereitstellung für die Microsoft Rights Management-Freigabeanwendung](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ScriptedInstall)

    -   [Überprüfen der erfolgreichen Installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted)

    -   [Deinstallationsbefehle](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_uninstallscripted)

    -   [Unterdrücken automatischer Updates](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SuppressAutomaticUpdates)

    -   [Nur Azure RMS: Konfigurieren der Dokumentenverfolgung](#BKMK_DocumentTracking)

    -   [Nur AD RMS: Unterstützung für mehrere E-Mail-Domänen innerhalb Ihrer Organisation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_FederatedDomains)

-   [Technische Übersicht für die Microsoft Rights Management-Freigabeanwendung](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_AdminOverview)

    -   [Schutzebenen – systemeigen und generisch](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_LevelsofProtection)

    -   [Unterstützte Dateitypen und Dateinamenerweiterungen](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SupportFileTypes)

    -   [Ändern der Standardschutzebene von Dateien](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ChangeDefaultProtection)

> [!TIP]
> Wenn Sie die RMS-Freigabe-App zum ersten Mal verwenden oder weitere Informationen suchen, finden Sie unter [So schützt RMS alle Dateitypen mithilfe der RMS-Freigabe-App](https://curah.microsoft.com/191031/how-rms-protects-all-file-types-by-using-the-rms-sharing-app) entsprechende Angaben.

Die RMS-Freigabeanwendung ist am besten für die Arbeit mit Azure RMS geeignet, da diese Bereitstellungskonfiguration das Senden geschützter Anhänge an Benutzer in einer anderen Organisation sowie Optionen, wie z. B. E-Mail-Benachrichtigungen und Dokumentenverfolgung mit Sperrung, unterstützt.  Sie funktioniert aber auch mit einigen Einschränkungen mit der lokalen Version AD RMS. Einen umfassenden Vergleich der Funktionen, die von Azure RMS und AD RMS unterstützt werden, finden Sie unter [Vergleich zwischen Azure Rights Management und AD RMS](https://technet.microsoft.com/library/jj739831.aspx). Wenn Sie AD RMS haben und zu Azure RMS migrieren möchten, finden Sie entsprechende Informationen unter [Migration von AD RMS zu Azure Rights Management](https://technet.microsoft.com/library/dn858447.aspx).

## <a name="BKMK_ScriptedInstall"></a>Automatische Bereitstellung für die Microsoft Rights Management-Freigabeanwendung
Die Windows-Version des RMS-Freigabeanwendung unterstützt eine skriptbasierte Installation, sodass sie auch für Unternehmensbereitstellungen geeignet ist.

Die einzige Voraussetzung für Installationen besteht darin, dass der Computer mindestens Windows 7 Service Pack 1 ausführt und dass mindestens das Microsoft-Framework Version 4.0 installiert ist. Wenn Sie Microsoft .NET Framework 4.0 installieren müssen, können Sie [es zur Installation über das Microsoft Download Center herunterladen](http://www.microsoft.com/download/details.aspx?id=17718).

#### So laden Sie die RMS-Freigabeanwendung für die automatische Bereitstellung herunter

1.  Klicken Sie auf der Seite [Microsoft Rights Management-Freigabeanwendung für Windows](http://www.microsoft.com/download/details.aspx?id=40857) im Microsoft Download Center auf **Herunterladen**.

2.  Wählen Sie die benötigten Dateien aus, um sie herunterzuladen. Es gibt zwei Clientinstallationspakete: eines für Windows 64-Bit Microsoft Rights Management sharing application x64.zip) und ein anderes für Windows 32-Bit (Microsoft Rights Management sharing application x86.zip).

3.  Extrahieren Sie die Dateien aus den komprimierten Installationspaketen, z. B. durch Doppelklicken. Kopieren Sie dann die extrahierten Dateien an einen Netzwerkspeicherort, auf den Clientcomputer zugreifen können.

Die Setuppakete für die RMS-Freigabeanwendung unterstützen verschiedene Bereitstellungsszenarien und enthalten Folgendes:

|Beschreibung|Bereitstellungsszenario|
|----------------|---------------------------|
|Microsoft-Onlinedienst-Anmeldungs-Assistent|Für Folgendes erforderlich:<br /><br />-   Office 2010 und Azure RMS<br />-   Office 2013 und Azure RMS, wenn Sie das [Update für Office 2013 vom 9. Juni 2015](https://support.microsoft.com/kb/3054853) (KB3054853) nicht installiert haben|
|Hotfix für Office (KB 2596501)|Für Folgendes erforderlich:<br /><br />-   Office 2010 und Azure RMS<br />-   Office 2010 und Active Directory RMS|
|Hotfix, damit der AD RMS-Client 1.0 zusammen mit Azure RMS funktioniert (KB 2843630)|Für Folgendes erforderlich:<br /><br />-   Office 2010 und Azure RMS<br />-   Office 2010 und Active Directory RMS|
|AD RMS-Client und die RMS-Freigabeanwendung|Für Folgendes erforderlich:<br /><br />-   Office 2016 oder Office 2013 und Azure RMS oder Active Directory RMS<br />-   Office 2010 und Azure RMS<br />-   Office 2010 und Active Directory RMS<br />-   Nur RMS-Freigabeanwendung und Office-Add-In|
|Office-Add-In für die Multifunktionsleiste|Für Folgendes erforderlich:<br /><br />-   Office 2016 oder Office 2013 und Azure RMS oder Active Directory RMS<br />-   Office 2010 und Azure RMS<br />-   Office 2010 und Active Directory RMS<br />-   Nur RMS-Freigabeanwendung und Office-Add-In|
|Vorbereitungstool für Azure Active Directory Rights Management|Für Folgendes erforderlich:<br /><br />-   Office 2010 und Azure RMS|
Verwenden Sie die folgenden Verfahren, um die Befehle, die zum Bereitstellen der RMS-Freigabeanwendung für diese Bereitstellungsszenarien erforderlich sind, zu identifizieren:

-   **Office 2016 oder Office 2013 und Azure RMS oder Active Directory RMS**

    Ihre Benutzer führen Office 2016 oder Office 2013 aus, Ihre Organisation verwendet Azure RMS oder Active Directory RMS, Benutzer arbeiten mit anderen Organisationen zusammen, die Azure RMS oder Active Directory RMS verwenden.

-   **Office 2010 und Azure RMS**

    Ihre Benutzer führen Office 2010 aus, Ihre Organisation verwendet Azure RMS, Benutzer arbeiten mit anderen Organisationen zusammen, die Azure RMS oder Active Directory RMS verwenden.

-   **Office 2010 und Active Directory RMS**

    Ihre Benutzer führen Office 2010 aus, Ihre Organisation verwendet AD RMS, Benutzer arbeiten mit anderen Organisationen zusammen, die Azure RMS verwenden.

-   **Nur RMS-Freigabeanwendung und Office-Add-In**

    Ihre Benutzer führen Office 2016, Office 2013 oder Office 2010 aus, Ihre Organisation verwendet AD RMS, Benutzer müssen nicht mit anderen Organisationen zusammenarbeiten, die Azure RMS verwenden. Mit dieser Installation können Sie nur die Freigabeanwendung und das Office-Add-In installieren.

> [!NOTE]
> Wenn Ihre Organisation in diesen Szenarien AD RMS verwendet, können die Benutzer geschützte Inhalte von anderen Organisationen, die Azure RMS verwenden, erhalten, aber die Benutzer können keine geschützten Inhalte an Benutzer in einer Organisation senden, die Azure RMS verwendet. Wenn Ihre Organisation aber Azure RMS ausführt, können die Benutzer geschützte Inhalte an andere bzw. von anderen Organisationen senden und empfangen.

Um die Installation für jedes Verfahren abzuschließen, muss der Computer neu gestartet werden. Sie können einen automatischen Neustart mit einem Befehl wie „shutdown /i“ initiieren.

#### So stellen Sie die RMS-Freigabeanwendung für Office 2016 oder Office 2013 und Azure RMS oder Active Directory RMS bereit

-   Führen Sie auf jedem Computer, auf dem Sie die RMS-Freigabeanwendung und zugehörige Komponenten installieren möchten, den folgenden Befehl mit erhöhten Rechten aus:

    ```
    setup.exe /s
    ```

Informationen zum Überprüfen des Erfolgs finden Sie im Abschnitt [Überprüfen der erfolgreichen Installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) dieses Themas.

#### So stellen Sie die RMS-Freigabeanwendung für Office 2010 und Azure RMS bereit

1.  Sie müssen der globale Administrator für Ihren Office 365- oder Azure Active Directory-Mandanten sein, damit Sie durch Ausführen des Vorbereitungstools für Azure Active Directory Rights Management die Zertifizierungsdienst-URL Ihrer Organisation abrufen können. Sie müssen dieses Tool nur ein Mal auf einem einzigen Computer ausführen. Sie verwenden die Zertifizierungsdienst-URL bei der Installation der RMS-Freigabeanwendung auf allen Computern:

    1.  Melden Sie sich an einem Computer mit einem lokalen Administratorkonto an.

    2.  Laden Sie auf diesem Computer [den Microsoft Online Services-Anmelde-Assistenten herunter, und installieren Sie ihn](http://www.microsoft.com/download/details.aspx?id=28177).

    3.  Führen Sie den folgenden Befehl aus, damit die Zertifizierungsdienst-URL, die Sie dann kopieren und für den nächsten Schritt speichern können, auf dem Bildschirm angezeigt wird:

        -   Für Windows 8.1 und Windows 8, 64-Bit:

            ```
            x64\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Für Windows 8.1 und Windows 8, 32-Bit:

            ```
            X86\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Für Windows 7, 64-Bit:

            ```
            x64\win7\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        > [!NOTE]
        > Dieser Befehl fordert Sie möglicherweise zur Eingabe Ihrer Anmeldeinformationen für Azure auf. Wenn der Computer nicht zu einer Domäne angehört, werden Sie aufgefordert. Wenn der Computer einer Domäne angehört, kann das Tool möglicherweise zwischengespeicherte Anmeldeinformationen verwenden.

2.  Führen Sie auf jedem Computer, auf dem Sie die RMS-Freigabeanwendung installieren werden, den folgenden Befehl mit erhöhten Rechten aus:

    ```
    setup.exe /s /configureO2010Admin /certificationUrl <certification_url>
    ```

3.  Auf jedem Computer, auf dem Sie die RMS-Freigabeanwendung installieren werden, müssen Benutzer den folgenden Befehl (ohne erhöhte Rechten) ausführen. Es gibt dazu verschiedene Möglichkeiten. Sie können Benutzer zum Ausführen des Befehls auffordern (z. B. durch einen Link in einer E-Mail-Nachricht oder im Helpdesk-Portal), oder Sie können ihn dem Anmeldeskript hinzufügen:

    ```
    bin\RMSSetup.exe /configureO2010Only
    ```

Informationen zum Überprüfen des Erfolgs finden Sie im Abschnitt [Überprüfen der erfolgreichen Installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) dieses Themas.

#### So stellen Sie die RMS-Freigabeanwendung für Office 2010 und Active Directory RMS bereit

1.  Führen Sie auf jedem Computer, auf dem Sie die RMS-Freigabeanwendung installieren werden, den folgenden Befehl mit erhöhten Rechten aus:

    ```
    setup.exe /s /configureO2010Admin
    ```

2.  Auf jedem Computer, auf dem Sie die RMS-Freigabeanwendung installieren werden, müssen Benutzer den folgenden Befehl (ohne erhöhte Rechten) ausführen. Es gibt dazu verschiedene Möglichkeiten. Sie können Benutzer zum Ausführen des Befehls auffordern (z. B. durch einen Link in einer E-Mail-Nachricht oder im Helpdesk-Portal), oder Sie können ihn dem Anmeldeskript hinzufügen:

    -   Für Windows 10, Windows 8.1 und Windows 8, 64-Bit:

        ```
        x64\aadrmprep.exe /configureO2010
        ```

    -   Für Windows 10, Windows 8.1 und Windows 8, 32-Bit:

        ```
        X86\aadrmprep.exe /configureO2010
        ```

    -   Für Windows 7, 64-Bit:

        ```
        x64\win7\aadrmpep.exe /configureO2010
        ```

Informationen zum Überprüfen des Erfolgs finden Sie im Abschnitt [Überprüfen der erfolgreichen Installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) dieses Themas.

#### So installieren Sie nur die RMS-Freigabeanwendung und das Office-Add-In

1.  Installieren Sie den AD RMS-Client und die RMS-Freigabeanwendung mithilfe des folgenden Befehls:

    -   Für 64-Bit-Windows:

        ```
        x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    -   Für 32-Bit-Windows:

        ```
        X86\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    Beispiel: `\\server5\apps\rms\x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "C:\Log files\ipviewerinstall.log"`

2.  Installieren Sie das Office-Add-In mithilfe der folgenden Befehle:

    -   Für die 64-Bit-Version von Office:

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "<log file path and name>"
        ```

    -   Für die 32-Bit-Version von Office:

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x86\Setup.msi" /L*v "<log file path and name>"
        ```

    Beispiel: `\\server5\apps\rms\msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "C:\Log files\rmsofficeinstall.log"`

Informationen zum Überprüfen des Erfolgs finden Sie im Abschnitt [Überprüfen der erfolgreichen Installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) dieses Themas.

### <a name="BKMK_verifyscripted"></a>Überprüfen der erfolgreichen Installation
Sie können die Installationsprotokolldateien zum Überprüfen der erfolgreichen Installation verwenden.

##### So überprüfen Sie die erfolgreiche Installation der RMS-Freigabeanwendung für Office 2016 oder Office 2013 und Azure RMS oder Active Directory RMS

-   Um den Erfolg des Befehls „Setup.exe“ auf den einzelnen Computern zu überprüfen, suchen Sie die Installationsprotokolldatei **RMInstaller.log** im Ordner *%temp%\RMS_installer_&lt;guid &gt;*, und identifizieren Sie dann den Exitcode.

    Eine erfolgreiche Installation hat einen Exitcode von 0. Jede andere Zahl weist auf eine fehlerhafte Installation hin.

    Beispielhafter Protokolldateiname: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0\RMInstaller.log**

##### So überprüfen Sie die erfolgreiche Installation der RMS-Freigabeanwendung für Office 2010 und Azure RMS

1.  Um den Erfolg des Befehls „Setup.exe“ auf den einzelnen Computern zu überprüfen, suchen Sie die Installationsprotokolldatei **RMInstaller.log** im Ordner *%temp%\RMS_installer_&lt;guid &gt;*, und identifizieren Sie dann den Exitcode.

    Eine erfolgreiche Installation hat einen Exitcode von 0. Jede andere Zahl weist auf eine fehlerhafte Installation hin.

    Beispielhafter Protokolldateiname: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  Um den Erfolg des Befehls „RMSSetup.exe“ zu überprüfen, muss der Benutzer die folgenden Dateien im Ordner *%localappdata%\microsoft\drm* erstellen:

    -   CERT-Machine-2048.drm

    -   CERT-Machine.drm

    -   CLC-&#42;.drm

    -   GIC-&#42;.drm

    Beispiel einer CLC-&#42;.drm-Datei:

    **CLC-alice@isvtenant999.onmicrosoft.com-{1b9cfccf;k5b11;k4a10;kac15;k29b2b6980f4c}.drm**

##### So überprüfen Sie die erfolgreiche Installation der RMS-Freigabeanwendung für Office 2010 und Active Directory RMS

1.  Um den Erfolg des Befehls „Setup.exe“ auf den einzelnen Computern zu überprüfen, suchen Sie die Installationsprotokolldatei im Ordner *%temp%\RMS_installer_&lt;guid&gt;*, und identifizieren Sie dann den Exitcode.

    Eine erfolgreiche Installation hat einen Exitcode von 0. Jede andere Zahl weist auf eine fehlerhafte Installation hin.

    Beispielhafter Protokolldateiname: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  Um den Erfolg des Befehls „aadrmprep.exe“ auf den einzelnen Computern zu überprüfen, suchen Sie den folgenden Text in der Installationsprotokolldatei: **aadrmprep.exe exited with status SUCCESS**.

    > [!NOTE]
    > In manchen Fällen kann diese Installation zweimal ausgeführt werden. Die erste Ausführung ist fehlerhaft, die zweite ist erfolgreich.

    Wenn Sie die durch dieses Tool an der Registrierung vorgenommenen Änderungen manuell überprüfen möchten, finden Sie sie hier:

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\ServiceLocation\Activation]

        @="&lt;certification url&gt;"

    -   [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\14.0\Common\DRM]

        DefaultUser="&lt;default_user&gt;"

##### So überprüfen Sie die erfolgreiche Installation der RMS-Freigabeanwendung nur für das Office-Add-In

1.  Um den Erfolg des Befehls „Setup_ipviewer.exe“ zu überprüfen, suchen Sie den folgenden Text in der Installationsprotokolldatei: **Installation success or error status: 0**

    Beispiel für Zeilen aus einer erfolgreichen Installation:

    **MSI (s) (F0:B8) [14:19:57:854]: Product: Active Directory Rights Management Services Client 2.1 -- Installation completed successfully.**

    **MSI (s) (F0:B8) [14:19:57:854]: Windows Installer installed the product. Product Name: Active Directory Rights Management Services Client 2.1. Product Version: 1.0.1179.1. Product Language: 1033. Hersteller: Microsoft Corporation. Installation success or error status: 0.**

2.  Um den Erfolg des Office-Add-Ins auf den einzelnen Computern zu überprüfen, suchen Sie den folgenden Text in der Installationsprotokolldatei: **Installation success or error status: 0**

    Beispiel für Zeilen aus einer erfolgreichen Installation:

    **MSI (s) (9C:88) [18:49:04:007]: Product: Microsoft RMS Office Addins -- Installation completed successfully.**

    **MSI (s) (9C:88) [18:49:04:007]: Windows Installer installed the product. Product Name: Microsoft RMS Office Addins. Product Version: 1.0.7. Product Language: 1033. Hersteller: Microsoft. Installation success or error status: 0.**

### <a name="BKMK_uninstallscripted"></a>Deinstallationsbefehle
Nicht alle Installationsbefehle, die für diese Bereitstellungen erforderlich sind, unterstützen einen Deinstallationsbefehl. Sie können den AD RMS-Client und die Freigabeanwendung deinstallieren, und Sie können das Office-Add-In deinstallieren. Verwenden Sie die folgenden Befehle, um diese Elemente zu deinstallieren.

##### So deinstallieren Sie den AD RMS-Client und die RMS-Freigabeanwendung

-   Verwenden Sie die folgenden Befehle:

    -   Für 64-Bit-Windows:

        ```
        x64\setup_ipviewer.exe /uninstall /quiet
        ```

    -   Für 32-Bit-Windows:

        ```
        x86\setup_ipviewer.exe /uninstall /quiet
        ```

##### So deinstallieren Sie das Office-Add-In

-   Verwenden Sie die folgenden Befehle:

    -   Für die 64-Bit-Version von Office:

        ```
        msiexec /x \x64\Setup[64].msi /quiet
        ```

    -   Für die 32-Bit-Version von Office:

        ```
        msiexec /x \x86\Setup.msi /quiet
        ```

### <a name="BKMK_SuppressAutomaticUpdates"></a>Unterdrücken automatischer Updates
Standardmäßig werden Benutzer benachrichtigt, wenn es eine neuere Version der RMS-Freigabeanwendung gibt, und dazu aufgefordert, sie herunterzuladen. Sie können diese Benachrichtigung unterdrücken, indem Sie den folgenden Registrierungsschlüssel bearbeiten:

1.  Navigieren Sie zu **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC**, und erstellen Sie, sofern nicht bereits vorhanden, einen neuen Schlüssel mit dem Namen **RmsSharingApp**.

2.  Wählen Sie **RmsSharingApp** aus, erstellen Sie einen neuen DWORD-Wert mit **AllowUpdatePrompt**, und legen Sie den Wert auf **0** fest.

Da die RMS-Freigabeanwendung nicht von WSUS unterstützt wird, können Sie das folgende Verfahren verwenden, um neue Versionen der RMS-Freigabeanwendung vor der Bereitstellung für alle Benutzer zu testen:

1.  Führen Sie auf allen Benutzercomputern ein Skript aus, um automatische Updates zu unterdrücken. Führen Sie dieses Skript auf den Computern, die Administratoren verwenden, um neue Versionen zu testen, nicht aus.

2.  Wenn eine neue Version verfügbar ist, können Administratoren sie herunterladen und testen.

3.  Wenn die Tests abgeschlossen sind und alle Probleme gelöst wurden, können Sie die neueste Version allen Benutzern mithilfe der Anweisungen zur automatischen Bereitstellung in diesem Handbuch bereitstellen.

### <a name="BKMK_DocumentTracking"></a>Nur Azure RMS: Konfigurieren der Dokumentenverfolgung
Wenn Sie ein [Abonnement haben, das Dokumentenverfolgung unterstützt](https://technet.microsoft.com/en-us/dn858608), ist die Website für die Dokumentenverfolgung standardmäßig für alle Benutzer in Ihrer Organisation aktiviert.  Die Dokumentenverfolgung zeigt Informationen, wie z. B. E-Mail-Adressen der Personen, die auf geschützte Dokumente zugegriffen haben, die von Benutzern freigegeben wurden, wann diese Benutzer versucht haben, darauf zuzugreifen, sowie deren Standort. Wenn das Anzeigen dieser Informationen in Ihrer Organisation aufgrund von Datenschutzanforderungen nicht zulässig ist, können Sie den Zugriff auf die Website der Dokumentenverfolgung mithilfe des Cmdlets  [Disable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623032) deaktivieren. Sie können den Zugriff auf die Website jederzeit mit dem Cmdlet [Enable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037) wieder aktivieren und mit [Get-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037) überprüfen, ob der Zugriff derzeit aktiviert oder deaktiviert ist.

 Zum Ausführen dieser Cmdlets benötigen Sie mindestens Version **2.3.0.0** des Azure RMS-Moduls für Windows PowerShell.  Installationsanweisungen finden Sie unter [Installieren von Windows PowerShell für Azure Rights Management](https://technet.microsoft.com/library/jj585012.aspx).

> [!TIP]
> Wenn Sie das Modul zuvor heruntergeladen und installiert haben, überprüfen Sie die Versionsnummer, indem Sie Folgendes ausführen: `(Get-Module aadrm –ListAvailable).Version`

Die folgenden URLs werden für die Dokumentenverfolgung verwendet und müssen zulässig sein (z. B. durch Hinzufügen zu Ihren vertrauenswürdigen Websites, wenn Sie Internet Explorer mit erhöhter Sicherheit verwenden):

-   https://&#42;.azurerms.com

-   https://ecn.dev.virtualearth.net

    > [!NOTE]
    > Dieser URL ist für Bing-Karten.

-   https://&#42;.microsoftonline.com

-   https://&#42;.microsoftonline-p.com

### <a name="BKMK_FederatedDomains"></a>Nur AD RMS: Unterstützung für mehrere E-Mail-Domänen innerhalb Ihrer Organisation
Wenn Sie AD RMS verwenden und Benutzer in Ihrer Organisation mehrere E-Mail-Domänen haben, möglicherweise aufgrund einer Fusion oder Übernahme, müssen Sie den folgenden Registrierungsschlüssel bearbeiten:

1.  Navigieren Sie zu **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC**, und erstellen Sie, sofern nicht bereits vorhanden, einen neuen Schlüssel mit dem Namen **RmsSharingApp**.

2.  Wählen Sie **RmsSharingApp** aus, erstellen Sie einen neuen mehrteiligen Zeichenfolgenwert namens **FederatedDomains**, und fügen Sie die Domänen und alle Unterdomänen hinzu, die Ihre Organisation verwendet. Platzhalter werden nicht unterstützt.

    Beispiel: Das Unternehmen Coho Vineyard &amp; Winery verfügt über die Standard-E-Mail-Domäne **cohovineyardandwinery.com**, aber durch Fusionen verwendet es auch die E-Mail-Domänen **cohowinery.com**, **eastcoast.cohowinery.com** und **cohovineyard**. Für die **FederatedDomains**-Wertdaten gibt der Administrator Folgendes ein: **cohowinery.com; eastcoast.cohowinery.com; cohovineyard**

Wenn Sie diese Registrierungsänderung nicht vornehmen, können Benutzer möglicherweise keine Inhalte nutzen, die von anderen Benutzern in ihrer Organisation geschützt wurden. Diese Bearbeitung der Registrierung ist nicht erforderlich, wenn Sie Azure RMS verwenden.

## <a name="BKMK_AdminOverview"></a>Technische Übersicht für die Microsoft Rights Management-Freigabeanwendung
Die Microsoft Rights Management-Freigabeanwendung ist eine optional herunterladbare Anwendung für Microsoft Windows und andere Plattformen, die Folgendes bereitstellt:

-   Schutz einer einzelnen Datei oder Massenschutz für mehrere Dateien sowie für alle Dateien in einem ausgewählten Ordner.

-   Vollständige Unterstützung für den Schutz beliebiger Dateitypen und einen integrierten Viewer für häufig verwendete Text- und Bilddateitypen.

-   Allgemeiner Schutz für Dateien, die RMS-Schutz nicht unterstützen.

-   Vollständige Interoperabilität mit Dateien, die mit Office Information Rights Management (IRM) geschützt sind.

-   Vollständige Interoperabilität mit PDF-Dateien, die mit SharePoint, FCI und unterstützten PDF-Erstellungstools geschützt sind.

Die Microsoft Rights Management-Freigabeanwendung verwendet die neue [AD RMS-Client 2.1-Runtime](http://www.microsoft.com/download/details.aspx?id=38396). Mithilfe der Funktionalität von AD RMS 2.1 stellt die Microsoft Rights Management-Freigabeanwendung Endbenutzern einen einfachen Schutz und eine einfache Nutzung bereit.

Ab der RMS-Version aus dem Oktober 2013 können Sie Dokumente systemeigen mithilfe von Office 2010 schützen und an andere Personen in einem anderen Unternehmen senden, die diese dann mithilfe von Azure RMS nutzen können. Darüber hinaus können Sie mit dieser Version bei Verwendung von AD RMS im Kryptografiemodus 2 RMS für Einzelpersonen verwenden und Inhalte von Personen in einem anderen Unternehmen, das Azure RMS verwendet, nutzen. Weitere Informationen zum Kryptografiemodus 2 finden Sie unter [AD RMS-Kryptografiemodi](http://technet.microsoft.com/library/hh867439%28v=ws.10%29.aspx).

### <a name="BKMK_LevelsofProtection"></a>Schutzebenen – systemeigen und generisch
Die Microsoft Rights Management-Freigabeanwendung unterstützt den Schutz auf zwei unterschiedlichen Ebenen, wie in der folgenden Tabelle beschrieben wird.

|Typ des Schutzes|Systemeigenes Format|Generisch|
|--------------------|------------------------|-------------|
|Beschreibung|Für Text-, Bild-, Microsoft Office- (Word, Excel, PowerPoint), PDF-Dateien und einige andere Anwendungsdateitypen, die AD RMS unterstützen, stellt der systemeigene Schutz eine starke Schutzebene bereit, die Verschlüsselung und Durchsetzung von Rechten (Berechtigungen) umfasst.|Für alle anderen Anwendungen und Dateitypen bietet der generische Schutz eine Schutzebene, die Dateiverkapselung mit dem PFILE-Dateityp und Authentifizierung umfasst, um zu überprüfen, ob ein Benutzer zum Öffnen der Datei autorisiert ist.|
|Schutz|Dateien werden vollständig verschlüsselt, und der Schutz folgendermaßen erzwungen:<br /><br />-   Bevor geschützter Inhalt gerendert wird, muss eine erfolgreiche Authentifizierung für diejenigen stattfinden, die die Datei per E-Mail oder Zugriffsberechtigung über Datei- oder Freigabeberechtigungen erhalten.<br />-   Außerdem werden Nutzungsrechte und Richtlinien, die vom Besitzer des Inhalts festgelegt werden, wenn Dateien geschützt werden, vollständig erzwungen, wenn der Inhalt im IP-Viewer (für geschützte Text- und Bilddateien) oder in der zugeordneten Anwendung (für alle anderen unterstützten Dateitypen) gerendert wird.|Dateischutz wird folgendermaßen erzwungen:<br /><br />-   Bevor geschützter Inhalt gerendert wird, muss eine erfolgreiche Authentifizierung für diejenigen stattfinden, die die Datei öffnen dürfen und Zugriff darauf haben. Wenn die Autorisierung fehlschlägt, wird die Datei nicht geöffnet.<br />-   Benutzerrechte und Richtlinien, die vom Besitzer des Inhalts festgelegt werden, werden angezeigt, um autorisierte Benutzer über die Richtlinie für die vorgesehene Verwendung zu informieren.<br />-   Überwachungsprotokollierung der autorisierten Benutzer, die auf Dateien zugreifen und diese öffnen, findet statt, es werden aber keine Nutzungsrechte durch nicht unterstützende Anwendungen erzwungen.|
|Standard für Dateitypen|Dies ist die Standardschutzebene für die folgenden Dateitypen:<br /><br />-   Text- und Bilddateien<br />-   Microsoft Office-Dateien (Word, Excel, PowerPoint)<br />-   Portable Document Format (PDF)<br /><br />Weitere Informationen finden Sie im folgenden Abschnitt: [Unterstützte Dateitypen und Dateinamenerweiterungen](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SupportFileTypes).|Dies ist der Standardschutz für alle anderen Dateitypen (z. B. VSDX, RTF und so weiter), die nicht durch den vollständigen Schutz unterstützt werden.|
Sie können die Standardschutzebene ändern, die die RMS-Freigabeanwendung anwendet. Sie können die Standardebene von systemeigen zu generisch oder von generisch zu systemeigen ändern und sogar verhindern, dass die RMS-Freigabeanwendung Schutz anwendet. Weitere Informationen finden Sie in diesem Thema im Abschnitt [Ändern der Standardschutzebene von Dateien](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ChangeDefaultProtection).

### <a name="BKMK_SupportFileTypes"></a>Unterstützte Dateitypen und Dateinamenerweiterungen
Die folgende Tabelle enthält die Dateitypen, die systemeigen von der Microsoft Rights Management-Freigabeanwendung unterstützt werden. Für diese Dateitypen wird die ursprüngliche Namenserweiterung geändert, wenn systemeigener Schutz angewendet wird, und diese Dateien schreibgeschützt werden.

Wenn die RMS-Freigabeanwendung darüber hinaus systemeigen eine Word-, Excel- oder PowerPoint-Datei schützt, die Benutzer durch Freigabe schützen, erstellt diese Aktion automatisch eine zweite Datei, die eine Kopie des Originals mit demselben Namen darstellt, aber mit der **PPDF**-Dateinamenerweiterung ¹. Diese Version der Datei stellt sicher, dass der Empfänger, die die RMS-Freigabeanwendung installiert, immer die Datei öffnen kann, die über systemeigenen Schutz verfügt.

Für Dateien, die generisch geschützt sind, wird die ursprüngliche Namenserweiterung immer in PFILE geändert.

> [!WARNING]
> Wenn Sie Firewalls, Webproxys oder Sicherheitssoftware haben, die Dateinamenerweiterungen überprüfen und entsprechende Maßnahmen ergreifen, müssen Sie diese möglicherweise zur Unterstützung der neuen Dateinamenerweiterungen neu konfigurieren.

|Ursprüngliche Dateinamenerweiterung|RMS-geschützte Dateinamenerweiterung|
|---------------------------------------|----------------------------------------|
|TXT|PTXT|
|XML|PXML|
|JPG|PJPG|
|JPEG|PPNG|
|PDF|.ppdf|
|PNG|PPNG|
|TIFF|PTIFF|
|BMP|PBMP|
|GIF|PGIF|
|GIFF|PGIFF|
|JPE|PJPE|
|JFIF|PJFIF|
|JIF|PJIF|
|JT|PJT|
¹ PDF-Rendering unterstützt von Foxit. Copyright © 2003–2014, Foxit Corporation.

In der folgende Tabelle werden die Dateitypen aufgeführt, die von der Microsoft Rights Management-Freigabeanwendung in Microsoft Office 2016, Office 2013 und Office 2010 systemeigen unterstützt werden. Für diese Dateitypen bleiben die Dateinamenerweiterungen nach dem Schutz der Dateien durch RMS unverändert.

|Von Office unterstützte Dateitypen|Von Office unterstützte Dateitypen|
|--------------------------------------|--------------------------------------|
|DOC<br /><br />DOCM<br /><br />DOCX<br /><br />DOT<br /><br />DOTM<br /><br />DOTX<br /><br />POTM<br /><br />POTX<br /><br />PPS<br /><br />PPSM<br /><br />PPSX<br /><br />PPT<br /><br />PPTM|PPTX<br /><br />THMX<br /><br />XLA<br /><br />XLAM<br /><br />XLS<br /><br />XLSB<br /><br />XLT<br /><br />XLSM<br /><br />XLSX<br /><br />XLTM<br /><br />XLTX<br /><br />XPS|

### <a name="BKMK_ChangeDefaultProtection"></a>Ändern der Standardschutzebene von Dateien
Sie können ändern, wie die RMS-Freigabeanwendung Dateien durch Bearbeiten der Registrierung schützt. Beispielsweise können Sie erzwingen, dass Dateien, die systemeigenen Schutz unterstützen, durch die RMS-Freigabeanwendung generisch geschützt werden.

Dafür kann es folgende Gründe geben:

-   Um sicherzustellen, dass alle Benutzer die Datei auf ihren mobilen Geräten öffnen können.

-   Um sicherzustellen, dass alle Benutzer die Datei öffnen können, wenn sie keine Anwendung haben, die systemeigenen Schutz unterstützt.

-   Um Sicherheitssysteme zu unterstützen, die Maßnahmen für Dateien anhand der Dateinamenerweiterung ergreifen und neu konfiguriert werden können, um die PFILE-Erweiterung zu unterstützen, aber nicht neu konfiguriert werden können, um mehrere Dateinamenerweiterungen für den systemeigenen Schutz zu unterstützen.

Auf ähnliche Weise können Sie erzwingen, dass die RMS-Freigabeanwendung systemeigenen Schutz auf Dateien anwendet, die in der Standardeinstellung durch generischen Schutz geschützt würden. Dies ist möglicherweise geeignet, wenn Sie eine Anwendung haben, die RMS-APIs unterstützt, zum Beispiel eine Line-of-Business-Anwendung, die von Ihren internen Entwicklern geschrieben wurde, oder eine Anwendung, die von einem unabhängigen Softwareanbieter (ISV) erworben wurde.

Sie können auch erzwingen, dass die RMS-Freigabeanwendung den Schutz von Dateien blockiert (der systemeigene oder generische Schutz wird nicht angewendet). Dies kann z. B. erforderlich sein, wenn Sie eine automatische Anwendung oder einen automatischen Dienst haben, die bzw. der eine bestimmte Datei öffnen muss, um ihren Inhalt zu verarbeiten. Wenn Sie den Schutz für einen Dateityp blockieren, können Benutzer die RMS-Freigabeanwendung nicht verwenden, um eine Datei mit diesem Dateityp zu schützen. Wenn sie es versuchen, wird eine Meldung angezeigt, dass der Administrator den Schutz verhindert hat, und sie müssen ihre Aktion zum Schutz der Datei abbrechen.

Nehmen Sie die folgenden Registrierungseinträge vor, um die RMS-Freigabeanwendung so zu konfigurieren, dass sie generischen Schutz auf alle Dateien anwendet, die in der Standardeinstellung durch systemeigenen Schutz geschützt würden.

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**: Erstellen Sie einen neuen Schlüssel namens **&#42;**.

    Diese Einstellung gibt Dateien mit beliebiger Erweiterung an.

2.  Erstellen Sie im neu hinzugefügten Schlüssel **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\&#42;** einen neuen Zeichenfolgenwert (REG_SZ) namens **Encryption** mit dem Datenwert **Pfile**.

    Diese Einstellung führt dazu, dass die RMS-Freigabeanwendung generischen Schutz anwendet.

Diese beiden Einstellungen führen dazu, dass die RMS-Freigabeanwendung generischen Schutz auf alle Dateien mit einer Dateinamenerweiterung anwendet. Wenn dies Ihr Ziel ist, ist keine weitere Konfiguration erforderlich. Sie können aber auch Ausnahmen für bestimmte Dateitypen definieren, damit diese weiterhin systemeigen geschützt werden. Zu diesem Zweck müssen Sie drei zusätzliche Registrierungseinträge für jeden Dateityp bearbeiten:

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**: Fügen Sie einen neuen Schlüssel mit dem Namen der Dateinamenerweiterung (ohne vorangestellten Punkt) hinzu.

    Für Dateien mit der Erweiterung „.docx“ erstellen Sie beispielsweise einen Schlüssel namens **DOCX**.

2.  Erstellen Sie im neu hinzugefügten Dateitypschlüssel **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX** einen neuen DWORD-Wert namens **AllowPFILEEncryption** mit dem Wert **0**.

3.  Erstellen Sie im neu hinzugefügten Dateitypschlüssel (z. B. **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX** einen neuen Zeichenfolgenwert namens **Encryption** mit dem Wert **Native**.

Durch diese Einstellungen sind alle Dateien generisch geschützt, mit Ausnahme der Dateien mit der Erweiterung DOCX, die systemeigen durch die RMS-Freigabeanwendung geschützt werden.

Wiederholen Sie diese drei Schritte für andere Dateitypen, die Sie als Ausnahmen definieren möchten, weil sie systemeigenen Schutz unterstützen und nicht durch die RMS-Freigabeanwendung generisch geschützt werden sollen.

Sie können ähnliche Registrierungseinträge für andere Szenarien durch Ändern des Werts der **Encryption**-Zeichenfolge vornehmen, die die folgenden Werte unterstützt:

-   **Pfile**: Allgemeiner Schutz

-   **Native**: systemeigener Schutz

-   **Off**: Schutz blockieren

## Siehe auch
[Rights Management-Freigabeanwendung – Benutzerhandbuch](../Topic/Rights_Management_sharing_application_user_guide.md)


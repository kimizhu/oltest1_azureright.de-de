---
description: na
keywords: na
title: RMS Client Deployment Notes
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 03cc8c6f-3b63-4794-8d92-a5df4cdf598f
---
# Anmerkungen zur Bereitstellung des RMS-Clients
Der RMS-Client, Version 2 (Rights Management Service, Rechteverwaltungsdienst) wird auch als MSIPC-Client bezeichnet. Es handelt sich um Software für Windows-Computer, die mit den Microsoft Rights Management Services, lokal oder in der Cloud, kommuniziert. Zweck ist der Schutz des Zugriffs auf die Nutzung von Informationen, die durch Anwendungen und Geräte fließen, und zwar innerhalb der Begrenzungen Ihrer Organisation oder außerhalb dieser verwalteten Begrenzungen. Zusätzlich zur Auslieferung mit der [Microsoft Rights Management-Freigabeanwendung](https://technet.microsoft.com/library/dn919648.aspx) steht der RMS-Client [als optionaler Download](http://www.microsoft.com/download/details.aspx?id=38396) zur Verfügung, der nach Bestätigen und Akzeptieren der Lizenzbedingungen kostenlos mit Drittanbietersoftware verteilt werden kann. Dadurch können Clients Inhalte schützen und nutzen, die durch RMS geschützt sind.

Dieses Thema enthält folgende Abschnitte:

-   [Weiterverbreiten des RMS-Clients](#BKMK_RedistributeInstaller)

-   [Installieren des RMS-Clients](#BKMK_InstallClient)

-   [Fragen und Antworten zum RMS-Client](#BKMK_QA)

-   [RMS-Clienteinstellungen](#BKMK_Settings)

-   [Nur AD RMS: Beschränken des RMS-Clients auf das Verwenden vertrauenswürdiger AD RMS-Server](#BKMK_UsingTrustedServers)

-   [RMS-Diensterkennung](#BKMK_ServiceDiscovery)

## <a name="BKMK_RedistributeInstaller"></a>Weiterverbreiten des RMS-Clients
Der RMS-Client kann kostenlos zusammen mit anderen Anwendungen und IT-Lösungen weiterverbreitet und gebündelt werden. Anwendungsentwickler und Lösungsanbieter, die den RMS-Client weiterverbreiten möchten, haben zwei Möglichkeiten:

-   Empfohlen: Einbettung des Installationsprogramms des RMS-Clients in die Anwendungsinstallation und Ausführung im unbeaufsichtigten Modus (der Schalter **/quiet** wird im nächsten Abschnitt detailliert vorgestellt).

-   Einrichten des RMS-Clients als Voraussetzung für die Anwendung. Bei dieser Option müssen Sie ggf. den Benutzern zusätzliche Anweisungen zum Abrufen, Installieren und Aktualisieren ihrer Computer mit dem RMS-Client bereitstellen, bevor sie Ihre Anwendung verwenden können.

## <a name="BKMK_InstallClient"></a>Installieren des RMS-Clients
Der RMS-Client befindet sich in einer ausführbaren Installer-Datei mit dem Namen **setup_msipc_***&lt;arch&gt;***.exe**, wobei *&lt;arch&gt;* entweder **x86** (für 32-Bit-Clientcomputer) oder **x64** (für 64-Bit-Clientcomputer) ist. Das 64-Bit-Installationspaket (x64) installiert eine ausführbare 32-Bit-Laufzeit für Kompatibilität mit 32-Bit-Anwendungen, die unter einem 64-Bit-Betriebssystem ausgeführt werden, sowie eine ausführbare 64-Bit-Laufzeit zur Unterstützung systemeigener 64-Bit-Anwendungen. Das 32-Bit-Installationsprogramm (x86) kann nicht in einer 64-Bit-Windows-Installation ausgeführt werden.

> [!NOTE]
> Für die Installation des RMS-Clients benötigen Sie erhöhte Berechtigungen, z. B. als Mitglied der Gruppe "Administratoren" auf dem lokalen Computer.

Sie können den RMS-Client mithilfe einer der folgenden Installationsmethoden installieren:

-   **Unbeaufsichtigter Modus.** Durch Verwendung des Schalters **/quiet** als Teil der Befehlszeilenoptionen können Sie den RMS-Client unbeaufsichtigt auf Clientcomputern installieren. Das folgende Beispiel zeigt eine unbeaufsichtigte Installation des RMS-Clients auf einem 64-Bit-Clientcomputer:

    ```
    setup_msipc_x64.exe /quiet
    ```

-   **Interaktiver Modus.** Alternativ können Sie den RMS-Client über das interaktive GUI-basierte Setup installieren, das vom Installations-Assistenten für den RMS-Client bereitgestellt wird. Hierfür müssen Sie auf Ihren lokalen Computer in dem Ordner auf das RMS-Client-Installationspaket (**setup_msipc_***&lt;arch&gt;***.exe**) doppelklicken, in den es auf Ihrem lokalen Computer kopiert oder heruntergeladen wurde.

## <a name="BKMK_QA"></a>Fragen und Antworten zum RMS-Client
Der folgende Abschnitt enthält häufig gestellte Fragen zum RMS-Client und die dazugehörigen Antworten.

### Welche Betriebssysteme unterstützen den RMS-Client?
Der RMS-Client wird von den folgenden Betriebssystemen unterstützt:

|Windows Server-Betriebssystem|Windows-Clientbetriebssystem|
|---------------------------------|--------------------------------|
|Windows Server 2012 R2|Windows 8,1|
|Windows Server 2012|Windows 8|
|Windows Server 2008 R2|Windows 7 mit mindestens SP1|
|Windows Server 2008 (nur AD RMS)|Windows Vista mit mindestens SP2 (nur AD RMS)|

### Welche Prozessoren oder Plattformen unterstützen den RMS-Client?
Der RMS-Client wird auf x86- und x64-Computerplattformen unterstützt.

### Wo wird der RMS-Client installiert?
In der Standardeinstellung wird der RMS-Client in "%ProgramFiles%\Active Directory Rights Management Services Client 2.&lt;Nebenversionsnummer&gt;" installiert.

### Welche Dateien sind der RMS-Clientsoftware zugeordnet?
Die folgenden Dateien werden als Teil der RMS-Clientsoftware installiert:

-   Msipc.dll

-   Ipcsecproc.dll

-   Ipcsecproc_ssp.dll

-   MSIPCEvents.man

Zusätzlich zu diesen Dateien werden mit dem RMS-Client auch Unterstützungsdateien für mehrsprachige Benutzeroberflächen in 44 Sprachen installiert. Wenn Sie überprüfen möchten, welche Sprachen unterstützt werden, führen Sie die Installation des RMS-Clients aus, und prüfen Sie nach Abschluss der Installation den Inhalt der Ordner für die mehrsprachige Unterstützung unter dem Standardpfad.

### Ist der RMS-Client standardmäßig enthalten, wenn ich ein unterstütztes Betriebssystem installiere?
Nein. Diese Version des RMS-Client wird als optionaler Download bereitgestellt, der separat auf Computern mit unterstützten Versionen des Betriebssystems Microsoft Windows installiert werden kann.

### Wird der RMS-Client von Microsoft Update automatisch aktualisiert?
Wenn Sie diesen RMS-Client mit der Option für die unbeaufsichtigte Installation installiert haben, übernimmt der RMS-Client Ihre aktuellen Einstellungen für Microsoft Update. Bei einer Installation des RMS-Clients mithilfe des GUI-basierten Setups werden Sie vom Installationsassistenten für den RMS-Client aufgefordert, Microsoft Update zu aktivieren.

## <a name="BKMK_Settings"></a>RMS-Clienteinstellungen
Der folgende Abschnitt enthält Einstellungsinformationen zum RMS-Client. Diese Informationen sind möglicherweise hilfreich, wenn Probleme mit Anwendungen oder Diensten haben, die den RMS-Client verwenden.

> [!NOTE]
> Einige Einstellungen hängen davon ab, ob die RMS-fähige Anwendung als Clientmodusanwendung (z. B. Microsoft Word und Outlook oder die RMS-Freigabeanwendung) oder Servermodusanwendung (z. B. SharePoint und Exchange) ausgeführt wird.  In den folgenden Tabellen werden diese Einstellungen als **Clientmodus** bzw. **Servermodus** bezeichnet.

### Speicherorte, an denen der RMS-Client Lizenzen auf Clientcomputern speichert
Der RMS-Client speichert Lizenzen auf dem lokalen Datenträger. Außerdem weden einige Informationen in der Windows-Registrierung zwischengespeichert.

|Beschreibung|Clientmoduspfade|Servermoduspfade|
|----------------|--------------------|--------------------|
|Speicherort von Lizenzen|%localappdata%\Microsoft\MSIPC|%allusersprofile%\Microsoft\MSIPC\Server\*&lt;SID&gt;*\|
|Speicherort von Vorlagen|%localappdata%\Microsoft\MSIPC\Templates|%allusersprofile%\Microsoft\MSIPC\Server\Templates\*&lt;SID&gt;*\|
|Speicherort in der Registrierung|HKEY_CURRENT_USER<br /> \Software<br /> \Classes<br /> \Local Settings<br /> \Software<br /> \Microsoft<br /> \MSIPC|HKEY_CURRENT_USER<br /> \Software<br /> \Microsoft<br /> \MSIPC<br /> \Server<br /> \*&lt;SID&gt;*|
> [!NOTE]
> *&lt;SID&gt;* ist die Sicherheitskennung (SID) für das Konto, unter dem die Serveranwendung ausgeführt wird. Wenn die Anwendung beispielsweise unter dem integrierten Netzwerkdienstkonto ausgeführt wird, ersetzen Sie *&lt;SID&gt;* durch den bekannten Wert der SID für dieses Konto (S-1-5-20).

### Windows-Registrierungseinstellungen für den RMS-Client
Sie können Windows-Registrierungsschlüssel zum Festlegen oder Ändern einiger RMS-Clientkonfigurationen verwenden. Als Administrator von RMS-fähigen Anwendungen, die mit AD RMS-Servern kommunizieren, können Sie beispielsweise den Dienstspeicherort im Unternehmen je nach aktuellem Speicherort des Clientcomputers in Ihrer Active Directory-Topologie aktualisieren (d. h. den AD RMS-Server außer Kraft seten, der aktuell für die Veröffentlichung ausgewählt ist). Oder Sie können AD RMS-Ablaufverfolgung auf dem Clientcomputer aktivieren, um das Beheben eines Problems mit einer RMS-fähigen Anwendung zu unterstützen. In der folgenden Tabelle finden Sie die Registrierungseinstellungen, die Sie für den RMS-Client ändern können.

|Aufgabe|Einstellung|
|-----------|---------------|
|Nur AD RMS: Aktualisieren des Speicherorts im Unternehmens für einen Clientcomputer|Aktualisieren Sie die folgenden Registrierungsschlüssel:<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterpriseCertification<br />    REG_SZ: default<br />    **Wert:**&lt;http oder https&gt;:// *RMS-Clustername*/_wmcs/Certification<br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterprisePublishing<br />    REG_SZ: default<br />    **Wert:**&lt;http oder https&gt;:// *RMS-Clustername*/_wmcs/Licensing|
|Aktivieren und Deaktivieren der Ablaufverfolgung|Aktualisieren Sie den folgenden Registrierungsschlüssel:<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC<br />    REG_DWORD: Trace<br />    **Wert:** 1 zum Aktivieren der Ablaufverfolgung, 0 zum Deaktivieren der Ablaufverfolgung (Standardwert)|
|Ändern der Häufigkeit (in Tagen), mit der Vorlagen aktualisiert werden|Mit den folgenden Registrierungswerten wird festgelegt, wie oft Vorlagen auf dem Computer des Benutzers aktualisiert werden, wenn der Wert "TemplateUpdateFrequencyInSeconds" nicht festgelegt ist.  Wenn keiner dieser Werte festgelegt ist, ist das Standardaktualisierungsintervall für Anwendungen, die den RMS-Client (Version 1.0.1784.0) zum Herunterladen von Vorlagen verwenden, 1 Tag. Bei Vorversionen dieser Version ist der Standardwert 7 Tage.<br /><br />**Clientmodus:**<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: TemplateUpdateFrequency<br />    **Wert:** Ein Ganzzahlwert, mit dem die Anzahl der Tage (mindestens 1) zwischen Downloads angegeben wird.<br /><br />**Servermodus:**<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*&lt;SID&gt;*<br />    REG_DWORD: TemplateUpdateFrequency<br />    **Wert:** Ein Ganzzahlwert, mit dem die Anzahl der Tage (mindestens 1) zwischen Downloads angegeben wird.|
|Ändern der Häufigkeit (in Sekunden), mit der Vorlagen aktualisiert werden **Important:** Wenn dies angegeben ist, wird der Wert für das Aktualisieren von Vorlagen in Tagen ignoriert. Geben Sie einen oder den anderen, aber nicht beide an.|Mit den folgenden Registrierungswerten wird festgelegt, wie oft Vorlagen auf dem Computer des Benutzers aktualisiert werden. Wenn dieser Wert oder der Wert zum Ändern der  Häufigkeit in Tagen (TemplateUpdateFrequency) nicht festgelegt ist, ist das Standardaktualisierungsintervall für Anwendungen, die den RMS-Client (Version 1.0.1784.0) zum Herunterladen von Vorlagen verwenden, 1 Tag. Bei Vorversionen dieser Version ist der Standardwert 7 Tage.<br /><br />**Clientmodus:**<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: TemplateUpdateFrequencyInSeconds<br />    **Wert:** Ein Ganzzahlwert, mit dem die Anzahl der Sekunden zwischen Downloads (mindestens 1) angegeben wird.<br /><br />**Servermodus:**<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*&lt;SID&gt;*<br />    REG_DWORD: TemplateUpdateFrequencyInSeconds<br />    **Wert:** Ein Ganzzahlwert, mit dem die Anzahl der Sekunden zwischen Downloads (mindestens 1) angegeben wird.|
|Nur AD RMS: Sofortiges Herunterladen der Vorlagen bei der nächsten Veröffentlichungsanforderung|Bei Tests und Bewertungen kann es wünschenswert sein, dass der RMS-Client Vorlagen so schnell wie möglich herunterlädt. Der folgende Registrierungsschlüssel kann entfernt werden, damit der RMS-Client Vorlagen sofort bei der nächsten Veröffentlichungsanfrage herunterlädt, anstatt auf den in der Registrierungseinstellung "TemplateUpdateFrequency" festgelegten Zeitpunkt zu warten:<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\&lt;Servername&gt;\Template **Note:** &lt;Servername&gt; kann sowohl externe (corprights.contoso.com) als auch interne (corprights) URLs und damit zwei verschiedene Einträge haben.|
|Nur AD RMS: Aktivieren der Unterstützung der Verbundauthentifizierung|Wenn der RMS-Clientcomputer mithilfe einer Verbundvertrauensstellung mit einem AD RMS-Cluster verbunden ist, müssen Sie den Verbundstartbereich konfigurieren.<br /><br />-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />    REG_SZ: FederationHomeRealm<br />    **Wert:** Der Wert dieses Registrierungseintrags ist der Uniform Resource Identifier (URI) für den Verbunddienst (z. B. https://fs-01.contoso.com).|
|Nur AD RMS: Unterstützen von Partnerverbundservern, die für Benutzereingaben die formularbasierte Authentifizierung erfordern|Standardmäßig wird der RMS-Client im unbeaufsichtigten Modus betrieben, in dem keine Benutzereingabe erforderlich ist. Partnerverbundserver können allerdings so konfiguriert werden, dass Benutzereingaben, z. B. über formularbasierte Authentifizierung, erforderlich sind. In diesem Fall muss der RMS-Client so konfiguriert werden, dass der unbeaufsichtigte Modus ignoriert wird, sodass das Formular für die Verbundauthentifizierung in einem Browserfenster angezeigt und der Benutzer für die Authentifizierung heraufgestuft wird.<br /><br />-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />    REG_DWORD: EnableBrowser **Note:** Wenn der Verbundserver für die formularbasierte Authentifizierung konfiguriert ist, ist dieser Schlüssel erforderlich. Wenn der Verbundserver für eine Verwendung der integrierten Windows-Authentifizierung konfiguriert ist, ist dieser Schlüssel nicht erforderlich.|
|Nur AD RMS: Blockieren der ILS-Dienstnutzung|Standardmäßig ermöglicht der RMS Client die Verwendung von durch den ILS-Dienst geschützten Inhalten. Er kann allerdings durch Einstellung des folgenden Registrierungsschlüssels so konfiguriert werden, dass dieser blockiert wird. Wenn dieser Registrierungsschlüssel für die Deaktivierung des ILS-Diensts festgelegt ist, wird bei allen Versuchen, vom ILS-Dienst geschützte Inhalte zu öffnen und zu nutzen, der folgende Fehler zurückgegeben:<br />HRESULT_FROM_WIN32(ERROR_ACCESS_DISABLED_BY_POLICY)<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: **DisablePassportCertification**<br />    **Wert:** 1 zum Blockieren der ILS-Nutzung, 0 zum Zulassen der ILS-Nutzung (Standardwert)|

### Verwalten der Vorlagenverteilung für den RMS-Client
Vorlagen erleichtern es Benutzern und Administratoren, im Handumdrehen den Rights Management-Schutz anzuwenden, und der RMS-Client lädt automatisch Vorlagen von den RMS-Servern oder -Services herunter. Wenn Sie die Vorlagen im folgenden Ordner ablegen, lädt der RMS-Client keine Vorlagen aus seinem Standardspeicherort herunter und lädt stattdessen die Vorlagen herunter, die Sie in diesem Ordner abgelegt haben. Der RMS-Client lädt möglicherweise weiterhin Vorlagen von anderen verfügbaren RMS-Servern herunter.

**Clientmodus:** %localappdata%\Microsoft\MSIPC\UnmanagedTemplates

**Servermodus:** %allusersprofile%\Microsoft\MSIPC\Server\UnmanagedTemplates\*&lt;SID&gt;*

Für das Verwenden dieses Ordners gibt es keine spezielle Benennungskonvention mit der Ausnahme, dass die Vorlage vom AD RMS-Server ausgegeben werden und mit der Dateinamenerweiterung XML benannt werden muss. Beispielsweise sind "Contoso-Confidential.xml" oder "Contoso-ReadOnly.xml" gültige Namen.

## <a name="BKMK_UsingTrustedServers"></a>Nur AD RMS: Beschränken des RMS-Clients auf das Verwenden vertrauenswürdiger AD RMS-Server
Der RMS-Client kann durch folgende Änderungen an der Windows-Registrierung auf dem lokalen Computer auf die Verwendung bestimmter vertrauenswürdiger AD RMS-Server beschränkt werden.

**So aktivieren Sie das Beschränken des RMS-Clients auf das Verwenden vertrauenswürdiger AD RMS-Server**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_DWORD: AllowTrustedServersOnly

    **Wert:** Wenn ein Wert ungleich Null angegeben wird, vertraut der RMS-Client nur den angegebenen Servern, die in der Liste "TrustedServers" und dem Azure Active Directory Rights Management-Dienst angegeben sind.

**So fügen Sie Mitglieder zur Liste vertrauenswürdiger AD RMS-Server hinzu**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_SZ: *&lt;URL_oder_Hostname&gt;*

    **Wert:** Die diesem Registrierungsschlüssel hinzugefügten Werte können entweder im DNS-Domänennamenformat (z. B. **adrms.contoso.com**) oder als vollständige URLs für vertrauenswürdige AD RMS-Server (z. B. **https://adrms.contoso.com**) angegeben werden. Wenn eine angegebene URL mit **https://** beginnt, verwendet der RMS-Client SSL oder TLS zum Kontaktieren des angegebenen AD RMS-Servers.

## <a name="BKMK_ServiceDiscovery"></a>RMS-Diensterkennung
Die RMS-Diensterkennung ermöglicht dem RMS-Client das Überprüfen, mit welchem RMS-Server oder -Dienst vor dem Schützen von Inhalten kommuniziert werden muss. Die Diensterkennung kann auch erfolgen, wenn der RMS-Client geschützte Inhalte nutzt. Dies ist allerdings weniger wahrscheinlich, da die den Inhalten zugeordnete Richtlinie den bevorzugten RMS-Server oder -Dienst enthält. Nur wenn dieser nicht erfolgreich ist, führt der Client die Diensterkennung aus.

Die Diensterkennung sucht zuerst nach einer lokalen Version von Rights Management (AD RMS). Wenn dies nicht erfolgreich ist, sucht die Diensterkennung automatisch für die Cloudversion von Rights Management (Azure RMS).

Um die Diensterkennung für eine lokale Bereitstellung durchzuführen, prüft der RMS-Client Folgendes:

1.  Die Windows-Registrierung auf dem lokalen Computer: Wenn Diensterkennungseinstellungen in der Registrierung konfiguriert sind, werden diese Einstellungen zuerst ausprobiert.  Standardmäßig sind diese Einstellungen nicht in der Registrierung konfiguriert.

2.  Active Directory-Domänendienste: Ein der Domäne beigetretener Computer fragt Active Directory auf einen Dienstverbindungspunkt ab. Wenn ein Dienstverbindungspunkt registriert ist, wird an den RMS-Client die URL des RMS-Servers zurückgegeben, die dieser verwenden soll

### Nur AD RMS: Aktivieren der serverseitigen Diensterkennung mithilfe von Active Directory
Wenn Ihr Konto über ausreichende Berechtigungen (Organisations-Admin und lokaler Administrator für den AD RMS-Server) verfügt, können Sie bei der Installation des AD RMS-Stammclusterservers einen Dienstverbindungspunkt automatisch registrieren. Wenn bereits ein AD RMS-Dienstverbindungspunkt in der Gesamtstruktur vorhanden ist, müssen Sie zunächst den vorhandenen Dienstverbindungspunkt löschen, ehe Sie einen neuen erstellen können.

Sie können nach der Installation von AD RMS mithilfe des folgenden Verfahrens einen Dienstverbindungspunkt registrieren und löschen. Bevor Sie beginnen, stellen Sie sicher, dass Ihr Konto die erforderlichen Berechtigungen (Organisations-Admin und lokaler Administrator für den AD RMS-Server) hat.

##### So aktivieren Sie die AD RMS-Diensterkennung durch Registrierung eines Dienstverbindungspunkts in Active Directory

1.  Öffnen Sie auf dem AD RMS-Server die Active Directory Management Services-Konsole:

    -   Wenn Sie Windows Server 2008 oder Windows Server 2008 R2 verwenden, klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory Rights Management Services**.

    -   Wenn Sie Windows Server 2012 R2 oder Windows Server 2012 verwenden, klicken Sie im Server-Manager auf **Extras** und dann auf **Active Directory Rights Management Services**.

2.  Klicken Sie in der AD RMS-Konsole mit der rechten Maustaste auf das AD RMS-Cluster, und klicken Sie dann auf **Eigenschaften**.

3.  Klicken Sie auf die Registerkarte **SCP**.

4.  Aktivieren Sie das Kontrollkästchen **SCP ändern**.

5.  Wählen Sie die Option **SCP auf aktuellen Zertifizierungscluster festlegen** aus, und klicken Sie auf **OK**.

### Aktivieren der clientseitigen Diensterkennung mithilfe der Windows-Registrierung
Als Alternative zur Verwendung eines Dienstverbindungspunkt oder für den Fall, dass ein solcher nicht vorhanden ist, kann die Registrierung auf dem Clientcomputer so konfiguriert werden, dass der RMS-Client seinen AD RMS-Server finden kann.

##### So aktivieren Sie die clientseitige AD RMS-Diensterkennung mithilfe der Windows-Registrierung

1.  Öffnen Sie den Windows-Registrierungseditor "Regedit.exe":

    -   Geben Sie auf dem Clientcomputer im Fenster "Ausführen" **regedit** ein, und drücken Sie dann die EINGABETASTE, um den Registrierungs-Editor zu öffnen.

2.  Navigieren Sie im Registrierungseditor zu **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC**.

    > [!IMPORTANT]
    > Wenn Sie eine 32-Bit-Anwendung auf einem 64-Bit-Computer ausführen, lautet der Pfad wie folgt: 
    > **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC**

3.  Klicken Sie zum Erstellen des Unterschlüssels "ServiceLocation" mit der rechten Maustaste auf **MSIPC**, zeigen Sie auf **Neu**, klicken Sie auf **Schlüssel**, und geben Sie dann **ServiceLocation** ein.

4.  Klicken Sie zum Erstellen des Unterschlüssels "EnterpriseCertification" mit der rechten Maustaste auf **ServiceLocation**, zeigen Sie auf **Neu**, klicken Sie auf **Schlüssel**, und geben Sie dann **EnterpriseCertification** ein.

5.  Doppelklicken Sie zum Festlegen der Unternehmenszertifizierungs-URL auf den Wert **(Standard)** unter dem Unterschlüssel **EnterpriseCertification**. Geben Sie, wenn das Dialogfeld **Zeichenfolge bearbeiten** angezeigt wird, als **Wertdaten**&lt;http or https&gt;://*AD RMS_cluster_name*/_wmcs/Certification ein, und klicken Sie dann auf **OK**.

6.  Klicken Sie zum Erstellen des Unterschlüssels "EnterprisePublishing" mit der rechten Maustaste auf **ServiceLocation**, zeigen Sie auf **Neu**, klicken Sie auf **Schlüssel**, und geben Sie dann EnterprisePublishing ein.

7.  Doppelklicken Sie zum Festlegen der Unternehmensveröffentlichungs-URL auf den Wert **(Standard)** unter dem Unterschlüssel **EnterprisePublishing**, und geben Sie, wenn das Dialogfeld **Zeichenfolge bearbeiten** angezeigt wird, als **Wertdaten**&lt;http or https&gt;://*AD RMS_cluster_name*/_wmcs/Licensing ein. Klicken Sie dann auf **OK**.

8.  Schließen Sie den Registrierungseditor.

Wenn der RMS-Client durch Abfragen von Active Directory keinen Dienstverbindungspunkt finden kann und ein solcher nicht in der Registrierung angegeben ist, haben Aufrufe der Diensterkennung für AD RMS keinen Erfolg.

### Umleiten des Datenverkehrs des Lizenzierungsservers
Mitunter müssen Sie ggf. Datenverkehr während einer Diensterkennung umleiten, z. B. wenn zwei Organisationen zusammengeführt werden und der alte Lizenzierungsserver in einer Organisation außer Betrieb genommen wird und Clients zu einem neuen Lizenzierungsserver umgeleitet werden müssen. Ein weiterer Fall ist die Migration von AD RMS zu Azure RMS. Gehen Sie folgendermaßen vor, um eine Umleitung von Lizenzierungsinformationen zu aktivieren.

##### So aktivieren Sie die Umleitung des AD RMS-Lizenzierungsservers mithilfe der Windows-Registrierung

1.  Öffnen Sie den Windows-Registrierungseditor "Regedit.exe":

    -   Geben Sie auf dem Clientcomputer im Fenster "Ausführen" **regedit** ein, und drücken Sie dann die EINGABETASTE, um den Registrierungs-Editor zu öffnen.

2.  Navigieren Sie im Registrierungseditor zu einem der folgenden Schlüssel:

    -   Für eine 64-Bit-Version von Office auf einer x64-Plattform: HKLM\SOFTWARE\Microsoft\MSIPC\Servicelocation

    -   Für eine 32-Bit-Version von Office auf einer x64-Plattform: HKLM\SOFTWARE\Wow6432Node\Microsoft\MSIPC\Servicelocation

3.  Erstellen Sie den Unterschlüssel "LicensingRedirection", indem Sie mit der rechten Maustaste auf **Servicelocation** klicken, auf **Neu** zeigen, auf **Schlüssel** klicken und dann **LicensingRedirection** eingeben.

4.  Klicken Sie zum Festlegen der Lizenzierungsumleitung mit der rechten Maustaste auf den Unterschlüssel **LicensingRedirection**, wählen Sie **Neu** aus, und wählen Sie dann **Zeichenfolgenwert** aus.  Geben Sie unter **Name** die vorherige Serverlizenzierungs-URL und als **Wert** die neue Serverlizenzierungs-URL an.

    Wenn Sie z. B. die Lizenzierungsdaten von einem Server bei Contoso.com auf einen Server bei Fabrikam.com umleiten möchten, könnten Sie die folgenden Werte eingeben:

    **Name:** `https://contoso.com/_wmcs/licensing`

    **Wert:** `https://fabrikam.com/_wmcs/licensing`

    > [!NOTE]
    > Wenn für den alten Lizenzserver sowohl eine Intranet- als auch eine Extranet-URL festgelegt sind, muss für beide URLs eine neue Name/Wert-Zuordnung unter dem Schlüssel "LicensingRedirection" festgelegt werden.

5.  Wiederholen Sie den vorherigen Schritt für alle Server, die umgeleitet werden müssen.

6.  Schließen Sie den Registrierungseditor.


---
description: na
keywords: na
title: Logging and Analyzing Azure Rights Management Usage
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a735f3f7-6eb2-4901-9084-8c3cd3a9087e
---
# Protokollieren und Analysieren der Nutzung von Azure Rights Management
In diesem Thema wird erläutert, wie Sie die Verwendungsprotokollierung bei Azure Rights Management (Azure RMS) verwenden können. Der Azure Rights Management-Dienst kann jede Anforderung protokollieren, die für Ihre Organisation durchgeführt wird. Hierzu gehören die Anforderungen von Benutzern, die von Rights Management-Administratoren in Ihrer Organisation ausgeführten Aktionen und die von Microsoft-Mitarbeitern ausgeführten Aktionen, mit denen Ihre Azure Rights Management-Bereitstellung unterstützt wird.

Sie können dann mithilfe der Azure Rights Management-Protokolle die folgenden Geschäftsszenarios unterstützen:

-   Analyse hinsichtlich geschäftlicher Erkenntnisse

    Azure Rights Management schreibt Protokolle im erweiterten W3C-Protokollformat in ein Azure-Speicherkonto, das von Ihnen bereitgestellt wird. Sie können diese Protokolle dann in ein Repository Ihrer Wahl leiten (z. B. eine Datenbank, ein OLAP-System (Online Analytical Processing) oder ein MapReduce-System), um die Informationen zu analysieren und Berichte zu erstellen. Beispielsweise könnten Sie identifizieren, wer auf Ihre RMS-geschützten Daten zugreift. Sie können bestimmen, auf welche RMS-geschützten Daten Benutzer zugreifen, von welchen Geräten aus und von wo. Sie können herausfinden, ob Benutzer geschützte Inhalte erfolgreich lesen können. Sie können ferner identifizieren, welche Personen ein wichtiges Dokument gelesen haben, das geschützt ist.

-   Überwachung auf Missbrauch

    Azure Rights Management-Protokollierungsinformationen stehen Ihnen praktisch in Echtzeit zur Verfügung, sodass Sie die Verwendung von Rights Management in Ihrem Unternehmen kontinuierlich überwachen können. 99,9 % der Protokolle sind innerhalb von 15 Minuten nach einer RMS-ausgelösten Aktion verfügbar.

    Beispielsweise können Sie sich benachrichtigen lassen, wenn ein plötzlicher Anstieg der Personen zu verzeichnen ist, die RMS-geschützte Daten außerhalb der Standardarbeitszeiten lesen, was darauf hindeuten kann, dass ein bösartiger Benutzer Informationen sammelt, um sie an die Konkurrenz zu verkaufen. Oder wenn derselbe Benutzer innerhalb eines kurzen Zeitraums offensichtlich von zwei verschiedenen IP-Adressen aus auf Daten zugreift, was darauf hindeuten kann, dass ein Benutzerkonto kompromittiert wurde.

-   Ausführen forensischer Analysen

    Wenn Sie ein Informationsleck haben, werden Sie wahrscheinlich gefragt, wer in der jüngsten Zeit auf bestimmte Dokumente zugegriffen hat, und auf welche Informationen eine verdächtigte Person zuletzt zugegriffen hat. Sie können diese Arten von Fragen beantworten, wenn Sie Azure Rights Management mit Protokollierung verwenden, weil Personen, die geschützte Inhalte verwenden, immer eine Rights Management-Lizenz abrufen müssen, um Dokumente und Bilder zu öffnen, die mit Azure Rights Management geschützt sind. Das gilt auch dann, wenn diese Dateien per E-Mail verschoben oder auf USB-Laufwerke oder andere Speichergeräte kopiert werden. Dies bedeutet, dass Sie Azure Rights Management-Protokolle als definitive Quelle für Informationen zur forensischen Analyse verwenden können, wenn Sie Ihre Daten mithilfe von Azure Rights Management schützen.

> [!NOTE]
> Wenn Sie nur an der Protokollierung von administrativen Aufgaben für Azure Rights Management interessiert sind, und nicht nachverfolgen möchten, wie die Benutzer Rights Management verwenden, können Sie das [Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx)-Cmdlet von Windows PowerShell für Azure Rights Management nutzen.
> 
> Sie können im klassischen Azure-Portal auch allgemeine Verwendungsberichte zur **RMS-Nutzung**, zu den **aktivsten RMS-Benutzern**, zur **Nutzung von RMS-Geräten** und zur **Nutzung RMS-fähiger Anwendungen** anzeigen. Klicken Sie für den Zugriff auf diese Berichte im klassischen Azure-Portal auf **Active Directory**, wählen und öffnen Sie ein Verzeichnis, und klicken Sie dann auf **BERICHTE**.

In den folgenden Abschnitten finden Sie Informationen zur Verwendungsprotokollierung von Azure Rights Management.

-   [Aktivieren der Verwendungsprotokollierung von Azure Rights Management](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_EnableRMSLogging)

-   [Zugreifen auf und Verwenden von Azure Rights Management-Verwendungsprotokollen](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_AccesAndUseLogs)

-   [Verwalten des Speichers für Azure Rights Management-Protokolle](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_ManageStorage)

-   [Delegieren des Zugriffs auf Azure Rights Management-Verwendungsprotokolle](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Delegate)

-   [Interpretieren von Azure Rights Management-Verwendungsprotokollen](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Interpret)

-   [Windows PowerShell-Referenz](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_PowerShell)

## <a name="BKMK_EnableRMSLogging"></a>Aktivieren der Verwendungsprotokollierung von Azure Rights Management
Die Verwendungsprotokollierung von Azure Rights Management ist optional. Wenn Sie sie verwenden möchten, müssen Sie bestimmte Schritte unternehmen. Beim Einsatz der Verwendungsprotokollierung von Azure Rights Management ändert sich die Funktionsweise von Rights Management nicht, und der Protokollierungsprozess selbst ist kostenfrei. Sie müssen aber ein Azure-Speicherkonto für die Protokolle angeben, und für diesen Speicher fallen Kosten an.

Stellen Sie vor Beginn sicher, dass Sie folgende Voraussetzungen für die Verwendung der Verwendungsprotokollierung von Azure Rights Management erfüllen:

|Anforderung|Weitere Informationen|
|---------------|-------------------------|
|Ein von der IT verwaltetes Abonnement einschließlich Azure Rights Management|Sie müssen ein Abonnement für Microsoft Azure Rights Management besitzen, das von Ihrer Organisation verwaltet wird. Organisationen, die RMS for Individuals verwenden, können die Verwendungsprotokollierung von Azure Rights Management nicht verwenden.<br /><br />Wenn es in Ihrer Organisation Benutzer gibt, die RMS for Individuals verwenden, ist die Verwendungsprotokollierung von Azure Rights Management ein sehr gutes geschäftliches Argument für einen Wechsel von RMS for Individuals zu einem Abonnement für Microsoft Azure Rights Management.<br /><br />Weitere Informationen zu den Abonnements mit enthaltenem Azure RMS finden Sie im Thema [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md) in Abschnitt [Cloud-Abonnements, die Azure RMS unterstützen](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions).<br /><br />Weitere Informationen zu RMS for Individuals finden Sie unter [RMS for Individuals und Azure Rights Management](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md).|
|Azure-Abonnement|Sie müssen ein Abonnement von Azure sowie ausreichenden Speicherplatz auf Azure besitzen, um Ihre Azure Rights Management-Protokolle zu speichern.|
|Windows PowerShell für Azure Rights Management|Falls noch nicht geschehen, müssen Sie das Windows PowerShell-Modul für Azure Rights Management herunterladen und installieren. Sie konfigurieren und verwalten Ihre Azure Rights Management-Verwendungsprotokolle mithilfe von Windows PowerShell-Cmdlets.<br /><br />Weitere Informationen finden Sie unter [Installieren der Windows PowerShell für Azure Rights Management](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md).|
Nutzen Sie das folgende Verfahren, um die Verwendungsprotokollierung von Azure Rights Management zu aktivieren. Es enthält auch Schritte, um ein Azure-Speicherkonto zu erstellen und dann Azure zur Verwendung dieses Speicherkontos für Ihre Rights Management-Protokolle zu konfigurieren.

> [!NOTE]
> Dieses Verfahren setzt voraus, dass Sie ein Azure-Konto besitzen. Die Verwendungsprotokollierung von Azure Rights Management unterstützt Einzelkonten, aber als bewährte Methode sollten Geschäfts- oder Schulkonten verwendet werden. Zusätzlich wird empfohlen, ein dediziertes Speicherkonto für Ihre Rights Management-Protokolle zu erstellen. Sie müssen die Speicherzugriffsschlüssel für Azure Rights Management und potenziell auch für andere Personen freigeben, wenn diese ebenfalls die Protokolldateien verwenden können sollen.
> 
> Weitere Informationen zum Azure-Speicher finden Sie unter der [Azure-Dokumentation für die Speicherung](http://azure.microsoft.com/documentation/services/storage/).

#### Erstellen eines Speicherkontos und Aktivieren der Verwendungsprotokollierung von Azure Rights Management

1.  Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) an.

2.  Wählen Sie im Hubmenu **Neu** -&gt; **Daten und Speicher** -&gt; **Speicherkonto**.

    > [!TIP]
    > Wenn Sie diese Option nicht sehen, prüfen Sie, ob Sie zusätzlich zu Ihrem Rights Management-Abonnement über ein Azure-Abonnement verfügen.

3.  Behalten Sie das Standardmodell **Klassisch** für die Bereitstellung bei, und klicken Sie auf **Erstellen**.

    Geben Sie einen Namen für das Speicherkonto an, und ändern Sie bei Bedarf die ausgewählten Optionen für **Tarif**, **Ressourcengruppe**, **Abonnement** und **An das Dashboard anheften**. Klicken Sie dann auf **ERSTELLEN**. Warten Sie, bis die Aktivität **Speicherkonto wird erstellt** abgeschlossen ist.

4.  Klicken Sie auf das neu erstellte Speicherkonto, und klicken Sie auf **Einstellungen**.

5.  Klicken Sie im Blatt **Einstellungen** auf das Symbol für **Schlüssel**.

6.  Kopieren Sie im Blatt **Schlüssel verwalten** den Wert von **PRIMÄRER ZUGRIFFSCHLÜSSEL**, und schließen Sie das Blatt.

7.  Starten Sie die Windows PowerShell mit der Option **Als Administrator ausführen**. Führen Sie den Befehl [Connect-AadrmService](https://msdn.microsoft.com/library/azure/dn629415.aspx) zum Verbinden mit dem Azure Rights Management-Dienst aus:

    ```
    Connect-AadrmService
    ```

8.  Verwenden Sie den Befehl [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx), um anzugeben, wo Ihre Azure Rights Management-Verwendungsprotokolle aufbewahrt werden sollen. Ersetzen Sie dabei *&lt;Access_Key&gt;* durch den primären Zugriffsschlüssel, den Sie in Schritt 6 kopiert haben, und *&lt;StorageAccount&gt;* durch den Namen des Speicherkontos, das Sie in Schritt 3 erstellt haben:

    ```
    $accesskey = convertto-securestring -asplaintext -force –string <Access_Key> Set-AadrmUsageLogStorageAccount -AccessKey $accesskey -StorageAccount <StorageAccount>
    ```

9. Verwenden Sie den Befehl [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx), um die Verwendungsprotokollierung von Azure Rights Management zu aktivieren:

    ```
    Enable-AadrmUsageLogFeature
    ```
    Folgende Meldung sollte angezeigt werden: **Das Verwendungsprotokollfeature ist für den Rights Management-Dienst aktiviert.**

Nachdem jetzt die Verwendungsprotokollierung aktiviert ist, beginnt Azure Rights Management, alle Aktionen für Ihre Organisation zu protokollieren, und speichert diese Informationen in Ihrem Speicherkonto. Vor diesem Zeitpunkt sind keine Protokollierungsinformationen verfügbar.

Weitere Informationen zum Erstellen von Speicherkonten finden Sie im Abschnitt [Erstellen eines Speicherkontos](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) des Artikels [Informationen zu Azure-Speicherkonten](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) in der Azure-Dokumentation.

## <a name="BKMK_AccesAndUseLogs"></a>Zugreifen auf und Verwenden von Azure Rights Management-Verwendungsprotokollen
Azure Rights Management schreibt Protokolle als eine Serie von BLOBs in Ihr Azure-Speicherkonto. Jedes BLOB enthält mindestens einen Protokolldatensatz im erweiterten W3C-Protokollformat. Die BLOB-Namen sind Zahlen in der Reihenfolge ihrer Erstellung. Im Abschnitt [Interpretieren von Azure Rights Management-Verwendungsprotokollen](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Interpret) weiter unten in diesem Dokument erhalten Sie weitere Informationen zu den Protokollinhalten und deren Erstellung.

Es kann einen Moment dauern, bis nach einer Azure Rights Management-Aktion Protokolle in Ihrem Speicherkonto angezeigt werden. Die meisten Protokolle werden innerhalb von 15 Minuten angezeigt.

Das Speicherkonto, das Sie für Ihre Azure Rights Management-Verwendungsprotokolle erstellt haben, verhält sich wie ein Postfach und unterstützt das direkte Lesen aus dem Speicherkonto. Es ist aber nicht für eine solche Verwendung optimiert. Stattdessen empfehlen wir für beste Leistung und zur Verringerung der Kosten, dass Sie die Protokolle in den lokalen Speicher herunterladen, z. B. einen lokalen Ordner, eine Datenbank oder ein MapReduce-Repository.

Es gibt zwei Möglichkeiten, um Ihre Verwendungsprotokolle herunterzuladen:

-   Verwenden Sie das Windows PowerShell-Cmdlet [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx).

    Dies ist die einfachste Methode, um auf Ihre Verwendungsprotokolle zuzugreifen. Dieses Cmdlet lädt Protokolle auf Ihren Computer herunter, wobei jedes BLOB als Datei an einen von Ihnen angegebenen Speicherort heruntergeladen wird.

-   Verwenden des [Azure Storage SDK](http://www.windowsazure.com/en-us/develop/net/) zum Schreiben der eigenen Anwendung, mit der Sie Protokolle herunterladen können.

    Eine benutzerdefinierte Anwendung kann höhere Flexibilität als das Cmdlet „Get-AadrmUsageLogs“ bieten. Vielleicht möchten Sie beispielsweise das Herunterladen von Protokollen an jemanden oder einen Prozess delegieren, der Ihre Administratoranmeldeinformationen für Azure Rights Management nicht verwenden darf. Oder Sie möchten die Protokolle in Echtzeit abrufen, weil Sie auf Missbrauch überwachen möchten.

#### So laden Sie Ihre Verwendungsprotokolle mit PowerShell herunter

-   Starten Sie die Windows PowerShell mit der Option **Als Administrator ausführen**, und führen Sie **Get-AadrmUsageLog –Path &lt;location&gt;** aus. Beispielsweise nach dem Erstellen eines Ordners mit dem Namen **logs** auf Laufwerk E:

    -   So laden Sie alle verfügbaren Protokolle in Ihren Ordner "E:\logs" herunter: `Get-AadrmUsageLog -Path "e:\logs"`

    -   So laden Sie einen bestimmten Bereich von Blobs herunter: `Get-AadrmUsageLog –Path "e:\logs" –FromCounter 1024 –ToCounter 2047`

Wenn Sie diese Cmdlets ausführen, zeigt die Windows PowerShell den Namen des letzten BLOBs an, der heruntergeladen wurde. Sie können diesen Namen einer Variablen zuweisen, mit der Sie „Get-AadrmUsageLog“ in einer Schleife oder einem geplanten Auftrag ausführen können, wobei jedes Mal nur die inkrementellen Protokolle heruntergeladen werden.

Beispiel:

**PS C:\&gt; $LastBlobName = Get-AadrmUsageLog –Path "e:\logs"**

**1527**

**PS C:\&gt; $LastBlobName**

**1527**

> [!TIP]
> Sie können mit [Microsofts Protokollparser](http://www.microsoft.com/download/details.aspx?id=24659) alle heruntergeladenen Protokolldateien in einem CSV-Format aggregieren. Dies ist ein Tool zum Konvertieren zwischen verschiedenen bekannten Protokollformaten. Sie können mit diesem Tool auch Daten in das SYSLOG-Format konvertieren oder in eine Datenbank importieren. Nachdem Sie das Tool installiert haben, führen Sie **LogParser.exe /?** aus, um Hilfe und Informationen zu diesem Tool anzuzeigen. Beispielsweise können Sie folgenden Befehl ausführen, um alle Informationen in eine Datei im LOG-Format zu importieren: **logparser –i:w3c –o:csv “SELECT &#42; INTO AllLogs.csv FROM &#42;.log”**.

Sie können die Verwendungsprotokollierung anhalten und fortsetzen. Wenn Sie die Protokollierung anhalten, behält Azure Rights Management Ihre Speicherkontoinformationen, sodass Sie die Protokollierung ganz einfach wieder fortsetzen können.

#### So halten Sie die Verwendungsprotokollierung an und setzen sie fort

-   Verwenden Sie zum Anhalten der Protokollierung folgendes Cmdlet: [Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   Verwenden Sie zum Fortsetzen der Protokollierung folgendes Cmdlet: [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   Verwenden Sie zum Überprüfen, ob die Protokollierung aktiviert oder deaktiviert ist, folgendes Cmdlet: [Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

    Der Wert **True** bedeutet, dass die Verwendungsprotokollierung für Azure Rights Management aktiviert ist, während der Wert **False** anzeigt, dass die Verwendungsprotokollierung deaktiviert ist.

## <a name="BKMK_ManageStorage"></a>Verwalten des Speichers für Azure Rights Management-Protokolle
Für den Speicherplatz, den Sie zum Aufbewahren Ihrer Azure Rights Management-Protokolle verwenden, werden Ihnen Kosten berechnet.

Azure Rights Management enthält keine Funktion zur automatischen Verwaltung der Verwendungsprotokolldateien. Wenn Sie keine Maßnahmen ergreifen, bleiben sie in Ihrem Speicherkonto. Um aber Speicherplatz zu erhalten und die Speicherkosten zu reduzieren, könnten Sie sie nach dem Herunterladen löschen. Oder Sie können auswählen, welche Dateien gelöscht werden sollen. Mit einer Ausnahme verwendet Azure Rights Management diese Protokolldateien nicht. Deshalb gibt es keine Einschränkungen dafür, wann Sie sie löschen können.

Die Datei, die Sie nicht löschen (oder ändern) dürfen, heißt **metadata** und befindet sich im Container **rms-metadata**. Azure Rights Management verwendet dieses BLOB, um die letzte verwendete BLOB-Nummer zu erfassen. Wenn diese Datei gelöscht wird, beginnt Azure Rights Management einen neuen Container für Protokolle mit einer BLOB-Nummer, die wieder bei 1 beginnt, und bei allen zukünftigen Downloads mit dem Cmdlet „Get-AadrmUsageLog“ wird dieser Container zum Herunterladen von Protokolldateien verwendet. Hieraus folgt, dass zwar alle Protokolle im Originalcontainer erhalten bleiben, aber verwaist sind. Die einzige Möglichkeit zum Herunterladen dieser verwaisten Protokolle besteht darin, das Azure Storage SDK zu verwenden.

> [!TIP]
> Statt Ihren Azure Rights Management-Protokollspeicher selbst zu verwalten, können Sie diese Verwaltungsfunktion an ein anderes Unternehmen delegieren, indem Sie Ihren Speicherkontonamen und den Zugriffsschlüssel freigeben. Weitere Informationen finden Sie in Abschnitt [Delegieren des Zugriffs auf Azure Rights Management-Verwendungsprotokolle](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Delegate) in diesem Thema.

Unter bestimmten Umständen möchten Sie eventuell Ihre Speicherkontoschlüssel neu generieren. Beispiel:

-   Sie wechseln das Unternehmen, das Ihre Azure Rights Management-Verwendungsprotokolle verwaltet.

-   Sie haben den Verdacht, dass Ihr Speicherzugriffsschlüssel kompromittiert wurde.

Wenn dies eintritt, verwenden Sie den sekundären Zugriffsschlüssel (unter der Voraussetzung, dass Sie zuvor den primären Zugriffsschlüssel verwendet haben), um die Dienstkontinuität zu gewährleisten. Wenn Sie einen zuvor nicht verwendeten Zugriffsschlüssel neu generieren, müssen Sie anschließend Azure Rights Management für die Verwendung des neuen Schlüssels konfigurieren. Verwenden Sie das folgende Verfahren, um den sekundären Zugriffsschlüssel neu zu generieren und Azure Rights Management für dessen Verwendung zu konfigurieren:

#### So generieren Sie den sekundären Zugriffsschlüssel neu

1.  Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) an.

2.  Klicken Sie auf **Alle Ressourcen**, und suchen Sie Ihren Speicher, indem Sie den Speichernamen in das Textfeld eingeben.

3.  Wählen Sie Ihren Speicher aus, und klicken Sie auf **Einstellungen**.

4.  Klicken Sie auf das Symbol für **Schlüssel**.

5.  Klicken Sie im Abschnitt **Schlüssel verwalten** auf **Sekundärschlüssel erneut generieren**, klicken Sie auf „Ja“, um zu bestätigen, dass Sie den sekundären Zugriffsschlüssel erneut generieren möchten, und kopieren Sie den neuen sekundären Zugriffsschlüssel in die Zwischenablage.

    Schließen Sie das Azure-Portal nicht.

6.  Starten Sie Windows PowerShell mit der Option **Als Administrator ausführen**, und verwenden Sie das Cmdlet [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx), um Azure Rights Management für die Verwendung dieses neuen Zugriffsschlüssels zu konfigurieren. Ersetzen Sie dabei *&lt;StorageAccount&gt;* durch den Namen Ihres Speicherkontos und *&lt;Access_Key&gt;* durch den neu generierten sekundären Zugriffsschlüssel, den Sie gerade kopiert haben:

    ```
    Set-AadrmUsageLogStorageAccount -StorageAccount <StorageAccount>-AccessKey <Access_Key>
    ```
    > [!WARNING]
    > Beim Ausführen dieses Befehls können Sie zwar zu einem anderen Speicherkonto wechseln, aber durch diese Aktion verwaisen Ihre vorherigen Protokolle, und Sie können dann nicht mehr mit dem Cmdlet „Set-AadrmUsageLogStorageAccount“ oder ähnlichen Verwaltungsbefehlen und -funktionen darauf zugreifen.

7.  Wechseln Sie zurück zum Azure-Portal, und generieren Sie im Abschnitt **Schlüssel verwalten** Ihren primären Zugriffsschlüssel neu.

Weitere Informationen zum Verwalten von Speicherkonten finden Sie im Abschnitt [Verwalten von Speicherzugriffsschlüsseln](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) des Artikels [Informationen zu Azure-Speicherkonten](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) in der Azure-Dokumentation.

## <a name="BKMK_Delegate"></a>Delegieren des Zugriffs auf Azure Rights Management-Verwendungsprotokolle
Sie können den Zugriff auf Ihre RMS-Protokolle delegieren, indem Sie Ihren Speicherkontonamen und den Zugriffsschlüssel freigeben. Sie können den Zugriff auch an einen anderen Administrator, einen Entwickler innerhalb Ihrer Organisation oder einen unabhängigen Softwarehersteller delegieren. Da diese nicht über Ihre RMS-Administratoranmeldeinformationen verfügen, können sie nicht das Cmdlet „Get-AardrmUsageLog“ verwenden, um die RMS-Protokolle herunterzuladen. Stattdessen müssen sie das Windows Storage SDK verwenden, um die Protokolle herunterzuladen. Alternativ können sie eine Anwendung schreiben, die die Protokolle direkt aus dem Azure-Speicher liest.

Das Freigeben Ihres Speicherkontonamens und des Zugriffsschlüssels auf diese Weise ist sicher, wenn das Speicherkonto dediziert für Ihre RMS-Protokolle bestimmt ist. Obgleich andere Personen auch Ihren Zugriffsschlüssel besitzen, können sie damit nicht auf ein anderes Speicherkonto zugreifen oder Ihr RMS-Mandantenkonto verwenden.

## <a name="BKMK_Interpret"></a>Interpretieren von Azure Rights Management-Verwendungsprotokollen
Verwenden Sie folgende Informationen als Hilfestellung bei der Interpretation der Azure Rights Management-Protokolle.

### Das Layout des Speicherkontos
Beim ersten Schreiben von Protokollen in Ihr Speicherkonto erstellt Azure Rights Management die folgenden beiden Container:

-   **Rms-metadata**: Dieser Container ist für Azure Rights Management reserviert. Dieser Container darf nicht geändert oder gelöscht werden.

-   **Rms-logs-&lt;GUID&gt;**: In diesem Container erstellt und speichert Azure Rights Management die Protokolle. Sie können alle Dateien in diesem Container problemlos löschen, wenn Sie die darin enthaltenen Protokollinformationen nicht mehr benötigen.

Im Laufe der Zeit erstellt Azure Rights Management möglicherweise zusätzliche **Rms-logs-&lt;GUID&gt;**-Container. Wenn beispielsweise der Container **Rms-metadata** beschädigt oder versehentlich gelöscht wird, setzt Azure Rights Management seinen Inhalt zurück und erstellt einen neuen Container **Rms-logs-&lt;GUID&gt;** für alle künftigen Protokolle. Die alten Protokolle im alten Container werden nicht gelöscht, sondern sind dann verwaist.

### Die Abfolge von Protokollen
Azure Rights Management schreibt die Protokolle als eine Serie von BLOBs. Jedes BLOB enthält mindestens einen Protokolldatensatz im erweiterten W3C-Protokollformat.

Der Name jedes BLOBs ist eine Nummer. Innerhalb jedes Protokollcontainers erhält das erste BLOB den Namen „000000001“. Jedes BLOB wird sequenziell in der Reihenfolge seiner Erstellung benannt. Jedes BLOB enthält mindestens einen Protokolldatensatz. Jeder Protokolldatensatz enthält einen UTC-Zeitstempel, der angibt, wann die entsprechende Anforderung von Azure Rights Management verarbeitet wurde.

> [!IMPORTANT]
> Das Protokollierungssystem von Azure Rights Management ist so optimiert, dass es die Protokolle möglichst schnell zur Verfügung stellt und die Reihenfolge dabei nicht streng beachtet wird. Die Reihenfolge der BLOBs sowie die Reihenfolge der Protokolldatensätze in einem BLOB kann nicht chronologisch sein. Der einzige Grund für die sequenzielle Benennung der BLOBs liegt darin, Ihnen das effiziente inkrementelle Herunterladen der Protokolle zu ermöglichen.
> 
> Zwei Beispiele für potenzielle Protokollsequenzergebnisse:
> 
> -   Die Protokolldatensätze in BLOB 000000004 können chronologisch mit den Protokolldatensätzen in BLOB 000000003 überlappen. In Extremfällen können alle Protokolldatensätze in BLOB 000000004 vor allen Protokolldatensätze in BLOB 000000003 generiert worden sein.
> -   Der zweite Protokolldatensatz in einem BLOB kann vor dem ersten Protokolldatensatz generiert worden sein, wurde aber in umgekehrter Reihenfolge in den Speicher geschrieben.

Bevor Sie Ihre Azure Rights Management-Protokolle analysieren, empfehlen wir Ihnen, die Protokolle herunterzuladen und in ein Repository zu importieren, wo Sie sie anhand ihrer Zeitstempel sortieren können. Weitere Informationen zum Herunterladen der Protokolle finden Sie in diesem Thema im Abschnitt [Zugreifen auf und Verwenden von Azure Rights Management-Verwendungsprotokollen](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_AccesAndUseLogs).

Da die Protokolle nicht notwendigerweise in chronologischer Reihenfolge sind, aber ihre Mehrheit innerhalb von 15 Minuten nach der Anforderung geschrieben werden, fügen Sie bei der Identifizierung der zu verwendenden Protokolle anhand ihres Zeitstempels 15 Minuten zu der Zeit, an der Sie interessiert sind, hinzu. Laden Sie dann diese Protokolle herunter. Diese Strategie sollte sicherstellen, dass Sie fast alle Protokolle erhalten.

Außerdem sollten Sie bedenken, ist, dass der Zeitstempel jedes Protokolldatensatzes die lokale Zeit des Azure Rights Management-Diensts widerspiegelt, der die Anforderung verarbeitet hat. Da Azure Rights Management auf mehreren Servern in mehreren Datencentern ausgeführt wird, scheinen die Protokolle manchmal nicht in der richtigen Reihenfolge zu sein, auch wenn sie nach Zeitstempel sortiert sind. Die Abweichung ist jedoch in der Regel gering und liegt im Bereich von einer Minute. In den meisten Fällen ist dies kein Problem, das sich nachteilig bei der Protokollanalyse manifestieren würde.

### Das BLOB-Format
Jedes BLOB ist im erweiterten W3C-Protokollformat. Es beginnt mit den folgenden zwei Zeilen:

**#Software: RMS**

**#Version: 1.1**

Die erste Zeile gibt an, dass es sich um Azure Rights Management-Protokolle handelt. Die zweite Zeile gibt an, dass der Rest des BLOBs die Spezifikation der Version 1.1 einhält. Wir empfehlen, dass alle Anwendungen, die diese Protokolle analysieren, diese beiden Zeilen überprüfen, bevor sie die Analyse des Rests des BLOBs fortsetzen.

In der dritten Zeile wird eine Liste von Feldnamen aufgezählt, die durch Tabstopps voneinander getrennt sind:

**#Fields: date            time            row-id        request-type           user-id       result          correlation-id          content-id                owner-email           issuer                     template-id             file-name                  date-published      c-info         c-ip**

Jede der folgenden Zeilen stellt einen Protokolldatensatz dar. Die Werte der Felder sind in derselben Reihenfolge wie die vorangehende Zeile, auch durch Tabstopps getrennt. Verwenden Sie die folgende Tabelle, um die Felder zu interpretieren.

|Feldname|W3C-Datentyp|Beschreibung|Beispielwert|
|------------|----------------|----------------|----------------|
|date|Datum|Das UTC-Datum, an dem die Anforderung verarbeitet wurde.<br /><br />Die Quelle ist die lokale Uhr auf dem Server, von dem die Anforderung bearbeitet wurde.|2013-06-25|
|time|Zeit|Die UTC-Zeit im 24-Stunden-Format, zu der die Anforderung verarbeitet wurde.<br /><br />Die Quelle ist die lokale Uhr auf dem Server, von dem die Anforderung bearbeitet wurde.|21:59:28|
|row-id|Text|Eindeutige GUID für diesen Protokolldatensatz.<br /><br />Dieser Wert ist hilfreich, wenn Sie Protokolle aggregieren oder in ein anderes Format kopieren.|1c3fe7a9-d9e0-4654-97b7-14fafa72ea63|
|request-type|Name|Der Name der angeforderten RMS-API.|AcquireLicense|
|user-id|String|Der Benutzer, der die Anforderung gesendet hat.<br /><br />Der Wert steht in einfachen Anführungszeichen. Manche Anforderungstypen sind anonym, wobei der Wert dann "" ist.|'joe@contoso.com'|
|result|String|„Success“, wenn die Anforderung erfolgreich verarbeitet wurde.<br /><br />Der Fehlertyp in einfachen Anführungszeichen zeigt an, wenn die Anforderung fehlgeschlagen ist.|'Success'|
|correlation-id|Text|Eine GUID, die das RMS-Clientprotokoll und das Serverprotokoll für eine bestimmte Anforderung gemeinsam haben.<br /><br />Dieser Wert kann bei der Behandlung von Clientproblemen hilfreich sein.|cab52088-8925-4371-be34-4b71a3112356|
|content-id|Text|Eine GUID in geschweiften Klammern, die den geschützten Inhalt identifiziert (z. B. ein Dokument).<br /><br />Dieses Feld hat nur dann einen Wert, wenn „request-type“ den Wert „AcquireLicense“ hat, und ist bei allen anderen Anforderungstypen leer.|{bb4af47b-cfed-4719-831d-71b98191a4f2}|
|owner-email|String|Die E-Mail-Adresse des Besitzers des Dokuments.|alice@contoso.com|
|issuer|String|Die E-Mail-Adresse des Ausstellers des Dokuments.|alice@contoso.com (oder) FederatedEmail.4c1f4d-93bf-00a95fa1e042@contoso.onmicrosoft.com|
|Template-id|String|ID der Vorlage, die zum Schützen des Dokuments verwendet wurde.|{6d9371a6-4e2d-4e97-9a38-202233fed26e}|
|File-name|String|Der Dateiname des geschützten Dokuments.|TopSecretDocument.docx|
|Date-published|Datum|Das Datum, an dem das Dokument geschützt wurde.|2015-10-15T21:37:00|
|c-info|String|Informationen zur Clientplattform, von der die Anforderung gesendet wird.<br /><br />Die spezifische Zeichenfolge variiert in Abhängigkeit von der Anwendung (z. B. Betriebssystem oder Browser).|'MSIPC;version=1.0.623.47;AppName=WINWORD.EXE;AppVersion=15.0.4753.1000;AppArch=x86;OSName=Windows;OSVersion=6.1.7601;OSArch=amd64'|
|c-ip|Adresse|Die IP-Adresse des Clients, von dem die Anforderung stammt.|64.51.202.144|

#### Ausnahmen für das Feld „user-id“
Obgleich das Feld „user-id“ normalerweise den Benutzer angibt, von dem die Anforderung stammt, gibt es zwei Ausnahmen, bei denen der Wert keinem echten Benutzer entspricht:

-   Der Wert **'microsoftrmsonline@&lt;IhreMandantenID&gt;.rms.&lt;Region&gt;.aadrm.com'**.

    Dies zeigt an, dass die Anforderung von einem Office 365-Dienst wie Exchange Online oder SharePoint Online stammt. In der Zeichenfolge steht *&lt;IhreMandantenID&gt;* für die GUID Ihres Mandanten und *&lt;Region&gt;* für die Region, in der Ihr Mandant registriert ist. Beispielsweise steht **Na** für Nordamerika, **Eu** für Europa und **ap** für Asien.

-   Wenn Sie den RMS-Verbindungsdienst verwenden.

    Anforderungen von diesem Connector werden mit dem Dienstprinzipalnamen protokolliert, der von RMS automatisch generiert wird, wenn Sie den RMS-Connector installieren.

#### Typische Anforderungstypen
Es gibt zahlreiche Anforderungstypen in Azure Rights Management. Die folgende Tabelle benennt und beschreibt einige der am häufigsten verwendeten Anforderungstypen.

|Anforderungstyp|Beschreibung|
|-------------------|----------------|
|AcquireLicense|Ein Client fordert von einem Windows-basierten Computer aus eine Lizenz für RMS-geschützten Inhalt an.|
|AcquirePreLicense|Ein Client fordert im Auftrag des Benutzers eine Lizenz für RMS-geschützten Inhalt an.|
|AcquireTemplates|Ein Aufruf wird ausgelöst, um Vorlagen anhand von Vorlagen-IDs abzurufen.|
|AcquireTemplateInformation|Ein Aufruf wird ausgelöst, um die IDs der Vorlage vom Dienst abzurufen.|
|AddTemplate|Vom klassischen Azure-Portal wird ein Aufruf zum Hinzufügen einer Vorlage ausgelöst.|
|BECreateEndUserLicenseV1|Von einem Mobilgerät wird ein Aufruf ausgelöst, um eine Endbenutzerlizenz zu erstellen.|
|BEGetAllTemplatesV1|Von einem Mobilgerät (Back-End) wird ein Aufruf ausgelöst, um alle Vorlagen abzurufen.|
|Certify|Der Client zertifiziert den Inhalt für den Schutz.|
|Decrypt|Der Client versucht, den RMS-geschützten Inhalt zu entschlüsseln.|
|DeleteTemplateById|Vom klassischen Azure-Portal wird ein Aufruf ausgelöst, um eine Vorlage nach Vorlagen-ID zu löschen.|
|ExportTemplateById|Vom klassischen Azure-Portal wird ein Aufruf ausgelöst, um eine Vorlage anhand einer Vorlagen-ID zu exportieren.|
|FECreateEndUserLicenseV1|Ähnlich wie bei der „AcquireLicense“-Anforderung, aber von mobilen Geräten aus.|
|FECreatePublishingLicenseV1|Identisch mit „Certify“ und „GetClientLicensorCert“ in Kombination, von mobilen Clients aus.|
|FEGetAllTemplates|Von einem Mobilgerät (Front-End) wird ein Aufruf ausgelöst, um die Vorlagen abzurufen.|
|GetAllTemplates|Vom klassischen Azure-Portal wird ein Aufruf ausgelöst, um alle Vorlagen abzurufen.|
|GetClientLicensorCert|Der Client fordert von einem Windows-basierten Computer aus ein Veröffentlichungszertifikat an (das später zum Schützen von Inhalt verwendet wird).|
|GetConfiguration|Ein Azure PowerShell-Cmdlet wird aufgerufen, um die Konfiguration des Azure RMS-Mandanten abzurufen.|
|GetConnectorAuthorizations|Von den RMS-Connectors wird ein Aufruf ausgelöst, um deren Konfiguration aus der Cloud abzurufen.|
|GetTenantFunctionalState|Das klassische Azure-Portal überprüft, ob Azure RMS aktiviert ist.|
|GetTemplateById|Vom klassischen Azure-Portal wird ein Aufruf ausgelöst, um eine Vorlage mit einer angegebenen Vorlagen-ID abzurufen.|
|ExportTemplateById|Vom klassischen Azure-Portal wird ein Aufruf ausgelöst, um eine Vorlage mit einer angegebenen Vorlagen-ID zu exportieren.|
|FindServiceLocationsForUser|Ein Aufruf zum Abfragen von URLs wird ausgelöst, die zum Aufrufen von „Certify“ oder von „AcquireLicense“ verwendet werden.|
|ImportTemplate|Vom klassischen Azure-Portal wird ein Aufruf zum Importieren einer Vorlage ausgelöst.|
|ServerCertify|Von einem RMS-fähigen Client (z. B. SharePoint) wird ein Aufruf zum Zertifizieren des Servers ausgelöst.|
|SetUsageLogFeatureState|Ein Aufruf zum Aktivieren der Verwendungsprotokollierung wird ausgelöst.|
|SetUsageLogStorageAccount|Ein Aufruf wird ausgelöst, um den Speicherort der Azure RMS-Protokolle anzugeben.|
|SignDigest|Ein Aufruf wird ausgelöst, wenn ein Schlüssel für Signaturzwecke verwendet wird. Dieser Aufruf erfolgt normalerweise einmal pro „AcquireLicence“ (oder „FECreateEndUserLicenseV1“), „Certify“ und „GetClientLicensorCert“ (oder „FECreatePublishingLicenseV1“).|
|UpdateTemplate|Vom klassischen Azure-Portal wird ein Aufruf zum Aktualisieren einer vorhandenen Vorlage ausgelöst.|

## <a name="BKMK_PowerShell"></a>Windows PowerShell-Referenz
Verwenden Sie folgende Windows PowerShell-Cmdlets zum Konfigurieren und Nutzen der Verwendungsprotokollierung von Azure Rights Management:

-   [Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx)

-   [Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

-   [Get-AadrmUsageLogLastCounterValue](https://msdn.microsoft.com/library/azure/dn629423.aspx)

-   [Get-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629419.aspx)

-   [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx)

Weitere Informationen zum Verwenden von Windows PowerShell für Azure Rights Management finden Sie unter [Verwalten von Azure Rights Management unter Verwendung der Windows PowerShell](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md).

## Siehe auch
[Verwenden von Azure Rights Management](../Topic/Using_Azure_Rights_Management.md)


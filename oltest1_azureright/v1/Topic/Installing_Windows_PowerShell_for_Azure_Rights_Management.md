---
description: na
keywords: na
title: Installing Windows PowerShell for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0d665ed6-b1de-4d63-854a-bc57c1c49844
---
# Installieren der Windows PowerShell f&#252;r Azure Rights Management
Verwenden Sie folgende Informationen als Hilfestellung bei der Installation von Windows PowerShell für Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS).

Sie können mithilfe dieses Windows PowerShell-Moduls [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] über die Befehlszeile verwalten, indem Sie einen Computer verwenden, der eine Internetverbindung besitzt und die im nächsten Abschnitt aufgeführten Voraussetzungen erfüllt. Windows PowerShell für [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] unterstützt die Skripterstellung für die Automatisierung oder kann für erweiterte Konfigurationsszenarien erforderlich sein. Weitere Informationen zu den Verwaltungsaufgaben und Konfigurationen, die das Modul unterstützt, finden Sie unter [Verwalten von Azure Rights Management unter Verwendung der Windows PowerShell](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md).

## Voraussetzungen
In dieser Tabelle werden die Voraussetzungen für die Installation und Verwendung von Windows PowerShell für [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] aufgeführt.

|Anforderung|Weitere Informationen|
|---------------|-------------------------|
|Eine Version von Windows, die das [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]-Administrationsmodul unterstützt|Überprüfen Sie die Liste der unterstützten Betriebssysteme im Bereich **Systemanforderungen** der [Downloadseite für das Azure Rights Management-Verwaltungstool](http://go.microsoft.com/fwlink/?LinkId=257721).|
|Mindestversion von Windows PowerShell: 2.0|Unterstützung für das [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]-Administrationsmodul wurde in Windows PowerShell 2.0 eingeführt.<br /><br />Standardmäßig werden die meisten Windows-Betriebssysteme mindestens mit Version 2.0 der Windows PowerShell installiert. Wenn Sie Windows PowerShell 2.0 installieren müssen, finden Sie Informationen dazu unter [Installieren von Windows PowerShell 2.0](http://msdn.microsoft.com/library/ff637750.aspx).<br /><br />Tipp: Sie können die von Ihnen ausgeführte Version der Windows PowerShell überprüfen, indem Sie in einer Windows PowerShell-Sitzung **$PSVersionTable** eingeben.|
|Mindestversion des Microsoft .NET Frameworks: 4.5<br /><br />Hinweis: Diese Version von Microsoft .NET Framework ist im Lieferumfang höherer Betriebssysteme enthalten. Deshalb sollten Sie eine manuelle Installation nur dann durchführen müssen, wenn Sie ein Clientbetriebssystem unter Windows 8.0 oder ein Serverbetriebssystem unter Windows Server 2012 verwenden.|Wenn die Mindestversion von Microsoft .NET Framework  noch nicht installiert ist, können Sie [Microsoft .NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653) herunterladen.<br /><br />Diese Mindestversion von Microsoft .NET Framework ist für einige der Klassen erforderlich, die das [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]-Administrationsmodul verwendet.|
|Microsoft Online Services-Anmelde-Assistent 7.0|Der Microsoft Online Services-Anmelde-Assistent ist für die [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]-Authentifizierung erforderlich.<br /><br />Weitere Informationen finden Sie unter [Download Center: Microsoft Online Services-Assistent für IT-Experten RTW](http://www.microsoft.com/en-us/download/details.aspx?id=41950).|

## Installieren des Rights Management-Administrationsmoduls

1.  Wechseln Sie zum Microsoft Download Center und [laden Sie das Azure Rights Management-Verwaltungstool herunter](https://go.microsoft.com/fwlink/?LinkId=257721), das das [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]-Verwaltungsmodul für Windows PowerShell enthält.

2.  Doppelklicken Sie in dem Ordner, in den Sie die [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]-Installationsprogrammdatei heruntergeladen und gespeichert haben, auf die ausführbare Datei, die Sie für Ihre Plattform (WindowsAzureADRightsManagementAdministration_x64.exe oder WindowsAzureADRightsManagementAdministration_x86.exe) heruntergeladen haben, um den Installationsassistenten für die Azure AD Rights Management-Administration zu starten.

3.  Schließen Sie den Assistenten ab.

Windows PowerShell für [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] ist jetzt installiert.

## Nächste Schritte
Um anzuzeigen, welche Cmdlets verfügbar sind, starten Sie die Windows PowerShell mit der Option **Als Administrator ausführen**, und geben Sie Folgendes ein:

```
Get-Command -Module aadrm
```
Verwenden Sie den Befehl `the Get-Help <cmdlet_name>`, um die Hilfe für ein bestimmtes Cmdlet anzuzeigen.

Weitere Informationen finden Sie unter:

-   Vollständige Liste verfügbarer Cmdlets: [Azure Rights Management-Cmdlets](https://msdn.microsoft.com/library/windowsazure/dn629398.aspx)

-   Liste der Hauptkonfigurationsszenarien, die Windows PowerShell unterstützen: [Verwalten von Azure Rights Management unter Verwendung der Windows PowerShell](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md)

Vor dem Ausführen von Befehlen, die den [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]-Dienst konfigurieren, müssen Sie mithilfe des [Connect-AadrmService](https://msdn.microsoft.com/library/windowsazure/dn629415.aspx)-Cmdlets eine Verbindung zum Dienst herstellen. Wenn Sie die gewünschten Konfigurationsbefehle ausgeführt haben, trennen Sie den Dienst mithilfe des [Disconnect-AadrmService](https://msdn.microsoft.com/library/windowsazure/dn629416.aspx)-Cmdlets.

> [!NOTE]
> Wenn Sie [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] noch nicht aktiviert haben, können Sie dies nach der Dienstverbindung mithilfe des Cmdlets [Enable-Aadrm](https://msdn.microsoft.com/library/windowsazure/dn629412.aspx) nachholen.

## Siehe auch
[Verwalten von Azure Rights Management unter Verwendung der Windows PowerShell](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md)


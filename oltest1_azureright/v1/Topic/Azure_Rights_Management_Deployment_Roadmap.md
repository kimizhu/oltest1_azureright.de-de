---
description: na
keywords: na
title: Azure Rights Management Deployment Roadmap
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 086600c2-c5d8-47ec-a4c0-c782e1797486
---
# Roadmap f&#252;r die Bereitstellung von Azure Rights Management
Führen Sie die folgenden Schritte aus, um Azure Rights Management (Azure RMS) für Ihre Organisation vorzubereiten, zu implementieren und zu verwalten.

Wenn Sie Azure RMS jedoch schnell einmal selbst ausprobieren möchten, statt es in eine Produktionsumgebung einzuführen, siehe [Schnellstart-Tutorial für Azure Rights Management](../Topic/Quick_Start_Tutorial_for_Azure_Rights_Management.md).

> [!IMPORTANT]
> Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md) gelesen haben.

## Schritt 1: Sicherstellen, dass Sie über ein Abonnement verfügen, das Azure Rights Management umfasst
Es gibt mehrere Abonnementtypen, die [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] einschließen. Weitere Informationen finden Sie im Abschnitt [Cloud-Abonnements, die Azure RMS unterstützen](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) im Thema [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md). Stellen Sie außerdem sicher, dass Ihr Abonnement die Funktionen umfasst, die Sie in Ihrer Organisation verwenden möchten, indem Sie die Tabelle unter [Vergleich der Rights Management Services (RMS)-Angebote](https://technet.microsoft.com/dn858608) heranziehen.

## Schritt 2: Vorbereiten Ihres Mandanten für die Verwendung von Rights Management
Bevor Sie mit der Verwendung von [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] beginnen, führen Sie folgende Vorbereitungsschritte aus:

1.  Stellen Sie sicher, dass Ihr Azure- oder Office 365-Mandant die Benutzerkonten und -gruppen enthält, die zum Authentifizieren von Benutzern in Ihrer Organisation durch Azure RMS verwendet werden. Falls erforderlich, erstellen Sie diese Konten und Gruppen, oder synchronisieren Sie diese über Ihr lokales Verzeichnis. Weitere Informationen finden Sie unter [Vorbereiten für Azure Rights Management](../Topic/Preparing_for_Azure_Rights_Management.md).

2.  Entscheiden Sie, ob Sie möchten, dass Microsoft Ihren Mandantenschlüssel verwaltet (Standard), oder ob Sie Ihren Mandantenschlüssel selber generieren und verwalten möchten (bekannt als BYOK, Bring Your Own Key). Beachten Sie, dass Sie derzeit BYOK nicht verwenden können, wenn Sie Exchange Online nutzen. Weitere Informationen finden Sie unter [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md).

3.  Installieren Sie das Windows PowerShell-Modul für [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] auf mindestens einem Computer, der Zugang zum Internet hat. Sie können diesen Schritt jetzt oder später durchführen. Weitere Informationen finden Sie unter [Installieren der Windows PowerShell für Azure Rights Management](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md).

4.  Wenn Sie derzeit lokale Rights Management Services verwenden: Führen Sie eine Migration aus, um die Schlüssel, Vorlagen und URLs in die Cloud zu verschieben. Weitere Informationen finden Sie unter [Migration von AD RMS zu Azure Rights Management](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md).

5.  Aktivieren Sie Rights Management, damit Sie mit der Verwendung des Diensts beginnen können. Wenn eine Bereitstellung in Phasen erforderlich ist, konfigurieren Sie benutzerbezogene Steuerungsrichtlinien für die Einbindung (Onboarding), um die Nutzung auf bestimmte Benutzer zu beschränken. Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](../Topic/Activating_Azure_Rights_Management.md).

Erwägen Sie optional die Konfigurierung folgender Funktionen:

-   Benutzerdefinierte Vorlagen, wenn die Standardvorlagen für Rechterichtlinien für Ihre Organisation nicht ausreichend sind. Sie können diesen Schritt jetzt oder später durchführen. Weitere Informationen finden Sie unter [Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md).

-   Nutzungsprotokollierung, sodass Sie überwachen können, wie Ihre Organisation Rights Management verwendet. Sie können diesen Schritt jetzt oder später durchführen. Weitere Informationen finden Sie unter [Protokollieren und Analysieren der Nutzung von Azure Rights Management](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md).

## Schritt 3: Konfigurieren Ihrer Anwendungen und Dienste für Rights Management
Die Konfiguration Ihrer Anwendungen kann das Installieren der Rights Management-Freigabeanwendung umfassen sowie die Aktivierung von Unterstützung für IRM-Features in SharePoint Online oder Exchange Online. Weitere Informationen finden Sie unter [Konfigurieren von Anwendungen für Azure Rights Management](../Topic/Configuring_Applications_for_Azure_Rights_Management.md).

Wenn Sie über vorhandene IT-Dienste verfügen, die von Azure RMS zu schützende Dateien überprüfen müssen (z. B. DLP-Lösungen, Gateways zur Inhaltsverschlüsselung und Antischadsoftware), konfigurieren Sie die Dienstkonten mit Administratorberechtigungen für Azure RMS. Weitere Informationen finden Sie unter [Konfigurieren von Administratoren für Azure Rights Management und Discovery Services oder die Datenwiederherstellung](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md).

Wenn Sie über lokale Dienste verfügen, die Sie mit Azure Rights Management verwenden möchten, installieren und konfigurieren Sie den Rights Management-Verbindungsdienst. Weitere Informationen finden Sie unter [Bereitstellen des Azure Rights Management-Verbindungsdiensts](../Topic/Deploying_the_Azure_Rights_Management_Connector.md).

## Schritt 4: Veröffentlichen und Nutzen rechtegeschützter Inhalte
Sie können jetzt geschützte Inhalte veröffentlichen und nutzen sowie die Nutzung von Rights Management durch Ihre Organisation protokollieren. Weitere Informationen finden Sie unter [Verwenden von Azure Rights Management](../Topic/Using_Azure_Rights_Management.md).

## Schritt 5: Bedarfsweises Verwalten von Rights Management für Ihr Mandantenkonto
Wenn Sie mit der Verwendung von [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] beginnen, kann das [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]-Modul für Windows PowerShell nützlich sein, um administrative Änderungen skriptgestützt oder automatisiert durchzuführen. Weitere Informationen finden Sie unter [Verwalten von Azure Rights Management unter Verwendung der Windows PowerShell](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md).

## Siehe auch
[Konfigurieren von Azure Rights Management](../Topic/Configuring_Azure_Rights_Management.md)


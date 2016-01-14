---
description: na
keywords: na
title: Preparing for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: afbca2d6-32a7-4bda-8aaf-9f93f5da5abc
---
# Vorbereiten f&#252;r Azure Rights Management
Nachdem Sie sich für ein Cloud-Abonnement registriert und Ihre Organisation mit einem Konto für [!INCLUDE[o365_1](../Token/o365_1_md.md)] oder Azure Active Directory eingerichtet haben, sind Sie bereit, um den [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]-Dienst zu aktivieren.

Vergewissern Sie sich aber vorher, dass folgende Punkte vorhanden sind:

-   Benutzerkonten und -gruppen in der Cloud, die Sie manuell erstellt haben oder die aus den Active Directory-Domänendiensten (AD DS) automatisch erstellt und synchronisiert wurden.

    Wenn Sie Ihre lokalen Konten und Gruppen synchronisieren, müssen nicht alle Attribute synchronisiert werden. Eine Liste der Attribute, die für Azure RMS synchronisiert werden müssen, finden Sie in diesem [Abschnitt zu Azure RMS](https://azure.microsoft.com/documentation/articles/active-directory-aadconnectsync-attributes-synchronized/) in der Azure Active Directory-Dokumentation. Zur Vereinfachung der Bereitstellung empfehlen wir die Verwendung von [Azure Connect AD](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) zum Verbinden Ihrer lokalen Verzeichnisse mit Azure Active Directory. Sie können aber auch jede andere Synchronisierungsmethode wählen, mit der dasselbe Ergebnis erzielt wird.

-   E-Mail-aktivierte Gruppen in der Cloud, die Sie für Rights Management verwenden möchten. Das können integrierte oder manuell erstellte Gruppen sein, die Benutzer enthalten, die Rights Management verwenden werden.

    Wenn Sie über Exchange Online verfügen, können Sie im Exchange Admin Center E-Mail-fähige Gruppen erstellen und nutzen. Wenn Sie AD DS haben und die Synchronisierung mit Azure AD vornehmen, können Sie E-Mail-fähige Gruppen erstellen und verwenden, die entweder Sicherheits- oder Verteilergruppen sind.

## Aktivieren von Rights Management
Standardmäßig ist [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] deaktiviert, wenn Sie sich für Ihr [!INCLUDE[o365_2](../Token/o365_2_md.md)]- oder Azure AD-Konto registrieren. Um [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] für Ihre Organisation zu aktivieren, müssen Sie den Dienst aktivieren. Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](../Topic/Activating_Azure_Rights_Management.md).

## Siehe auch
[Konfigurieren von Azure Rights Management](../Topic/Configuring_Azure_Rights_Management.md)


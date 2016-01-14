---
description: na
keywords: na
title: Scenario - Retain Control of Documents Stored in SharePoint
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1b6244c7-5ab9-4881-bc8f-6fa960390d89
---
# Szenario – Beibehalten der Kontrolle &#252;ber in SharePoint gespeicherte Dokumente
Dieser Abschnitt enthält Anweisungen für Administratoren und einen Leitfaden für Benutzeranweisungen.Sie müssen sich mit den Anweisungen für Administratoren vertraut gemacht haben, ehe Sie Ihre Benutzer über diese Konfiguration informieren.

## Anweisungen für Administratoren
![](../Image/AzRMS_AdminBanner.png)

Befolgen Sie diese Anweisungen, um sicherzustellen, dass Office-Dokumente, die in SharePoint gespeichert sind, mithilfe geschützter Bibliotheken unter Ihrer Kontrolle bleiben.Die Dokumente werden beispielsweise automatisch vor durch Benutzer versehentlich oder beabsichtigt verursachte Datenlecks geschützt, und Sie können den Zugriff auf Inhalte blockieren, auch nachdem sie heruntergeladen oder synchronisiert wurden.Die Dateien, die Sie schützen möchten, dienen möglicherweise der Zusammenarbeit an Entwurfsdokumenten oder Plänen oder gehören zum Lieferumfang.Wenn Sie geschützte Bibliotheken für SharePoint konfigurieren, werden die darin gespeicherten Office-Dateien von Azure Rights Management geschützt.

Die Anweisungen sind unter den folgenden Umständen geeignet:

-   Mitarbeiter nutzen Office-Dokumente gemeinsam und arbeiten zusammen daran.

-   Die Dokumente enthalten Informationen, die nicht öffentlich, aber nicht unbedingt ausschließlich für die interne Verwendung vorgesehen sind.

-   Mitarbeiter müssen nicht die Berechtigungen festlegen oder ändern, die ein Administrator auf Bibliotheksebene festlegt.

## Anforderungen bei diesem Szenario
Damit dieses Szenario funktioniert, muss Folgendes vorhanden sein:

|Prüfung|Anforderung|Wenn Sie weitere Informationen benötigen|
|-----------|---------------|--------------------------------------------|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Sie haben Konten und Gruppen für Office 365 oder Azure Active Directory vorbereitet.|[Vorbereiten für Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Azure Rights Management ist aktiviert.|[Aktivieren von Azure Rights Management](https://technet.microsoft.com/library/jj658941.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Wenn Sie SharePoint Server verwenden möchten: Stellen Sie den RMS-Connector bereit, und konfigurieren Sie ihn für SharePoint.|[Bereitstellen des Azure Rights Management-Connectors](https://technet.microsoft.com/library/dn375964.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Konfigurieren Sie SharePoint für IRM und geschützte Bibliotheken.|[Einrichten der Verwaltung von Informationsrechten (IRM) im SharePoint Admin Center](https://support.office.com/en-us/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239ce6eb-4e81-42db-bf86-a01362fed65c)<br /><br />[Anwenden der Verwaltung von Informationsrechten (IRM) auf eine Liste oder Bibliothek](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)|

## Benutzeranweisungen
Es gibt keine spezifischen Benutzeranweisungen für dieses Szenario, da geschützte Bibliotheken keine besondere Aktionen von Benutzern verlangen.Dokumente sind automatisch entsprechend den Berechtigungen geschützt, die ein SharePoint-Administrator für den Standort festlegt.Allerdings müssen Sie die Benutzer und das Helpdesk informieren, welche Bibliotheken geschützt sind und wie dies ihre Nutzung der Dokumente einschränken kann.Aufgrund derzeit geltender Einschränkungen können diese Dokumente auf mobilen Geräten zwar angezeigt, aber nicht bearbeitet werden.

Das folgenden Beispiel kann als Standard-E-Mail-Nachricht an die entsprechende Abteilung oder das Team gesendet werden, nachdem eine SharePoint-Bibliothek für die Verwendung von Azure RMS konfiguriert wurde.

### Beispielbenutzerdokumentation
![](../Image/AzRMS_ExampleBanner.png)

##### IT-Ankündigung: Änderungen an der Website "Vertriebsprognosen und Berichte"

-   Die SharePoint-Website **Vertriebsprognosen und Berichte** ist jetzt für die sichere Zusammenarbeit konfiguriert.Von nun an müssen Sie die auf dieser Website gespeicherten Kalkulationstabellen und Word-Dokumente direkt bearbeiten. Sie können sie beispielsweise nicht zur Bearbeitung an einem anderen Speicherort speichern oder per E-Mail an Dritte senden.Sie können sie auf mobilen Geräten anzeigen, müssen aber einen Windows-Computer verwenden, um sie zu bearbeiten.

**Benötigen Sie Unterstützung?**

-   Wenden Sie sich an das Helpdesk: helpdesk@vanarsdelltd.com


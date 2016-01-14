---
description: na
keywords: na
title: Frequently Asked Questions for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71ce491f-41c1-4d15-9646-455a6eaa157d
---
# H&#228;ufig gestellte Fragen zu Azure Rights Management
Einige häufig gestellte Fragen zu Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)], das auch als Azure RMS bezeichnet wird:

## Was benötige ich, um Azure RMS bereitzustellen, und wie stelle ich das an?
Überprüfen Sie zunächst [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md). Darin sind Informationen über Cloud-Abonnementoptionen enthalten, und es wird gezeigt, wie Sie Ihre lokalen Server mit Azure RMS verwenden können, welche Bereitstellungsszenarien zurzeit nicht unterstützt werden und welche Geräte und Anwendungen Azure RMS unterstützen. Zudem enthält das Thema einen Link für den Fall, dass Sie eine Liste von IP-Adressen und Domänennamen für Firewalls oder Proxyserver benötigen. Es kann darüber hinaus sinnvoll sein, die anderen Themen im Abschnitt [Erste Schritte mit Azure Rights Management](../Topic/Getting_Started_with_Azure_Rights_Management.md) anzusehen, um ein grundlegendes Verständnis dafür zu entwickeln, wie [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] den Schutz der Daten Ihrer Organisation unterstützen kann, wie es sich im Vergleich zur lokalen Version von Active Directory Rights Management verhält und welche Begriffe und Abkürzungen für [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] spezifisch sind.

Wenn Sie dann bereit sind, Azure RMS selbst zu testen oder es für Ihre Organisation bereitzustellen, verwenden Sie die [Roadmap für die Bereitstellung von Azure Rights Management](../Topic/Azure_Rights_Management_Deployment_Roadmap.md), die eine Liste mit Schritten und Links zu weiteren Informationen sowie Anweisungen zur Umsetzung enthält.

Weitere Informationen, Ressourcen und Supportoptionen finden Sie unter [Informationen zu und Unterstützung für Azure Rights Management](../Topic/Information_and_Support_for_Azure_Rights_Management.md).

## Kann ich Azure RMS in meine lokalen Server integrieren?
Ja. Azure RMS kann in Ihre lokalen Server, etwa Exchange Server, SharePoint und Windows-Dateiserver, integriert werden. Dazu verwenden Sie den [Rights Management-Connector](https://technet.microsoft.com/library/dn375964.aspx). Wenn Sie nur an der Nutzung der Dateiklassifizierungsinfrastruktur (FCI, File Classification Infrastructure) mit Windows Server interessiert sind, können Sie auch die [RMS Protection-Cmdlets](https://technet.microsoft.com/library/mt601315%28v=ws.10%29.aspx) verwenden. Sie können Ihre Active Directory-Domänencontroller auch mit Azure AD synchronisieren und zusammenführen, um eine übergangslosere Authentifizierungshandhabung für Benutzer zu erreichen. Dazu können Sie beispielsweise [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) verwenden.

Azure RMS generiert und verwaltet XrML-Zertifikate automatisch nach Bedarf, sodass es keine lokale PKI verwendet. Weitere Informationen dazu, wie Azure RMS Zertifikate verwendet, finden Sie im Abschnitt [Exemplarische Vorgehensweise zur Funktionsweise von Azure RMS: Erste Verwendung, Inhaltsschutz, Inhaltsaufnahme](../Topic/What_is_Azure_Rights_Management_.md#BKMK_Walthrough) im Thema [Was ist Azure Rights Management?](../Topic/What_is_Azure_Rights_Management_.md).

## Ich habe eine Hybridbereitstellung von Exchange mit einigen Benutzern auf Exchange Online und anderen auf Exchange Server – wird dies von Azure RMS unterstützt?
Ja, und das Gute ist, dass Benutzer über zwei Exchange-Bereitstellungen hinweg E-Mails und Anlagen nahtlos schützen sowie geschützte E-Mails und Anlagen nutzen können. Führen Sie für diese Konfiguration folgende Schritte aus: [Aktivieren von Azure RMS](https://technet.microsoft.com/library/jj658941.aspx), [Aktivieren von IRM für Exchange Online](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx) und [Bereitstellen und Konfigurieren des RMS-Connectors](https://technet.microsoft.com/library/dn375964.aspx) für Exchange Server.

## Wenn ich Azure RMS in der Produktion bereitstelle, ist mein Unternehmen dann an die Lösung gebunden und läuft andernfalls Gefahr, den Zugriff auf Inhalte zu verlieren, die wir mit Azure RMS geschützt haben?
Nein, Sie behalten immer die Kontrolle über Ihre Daten und können weiterhin darauf zugreifen, selbst wenn Sie sich entscheiden, Azure RMS nicht mehr zu verwenden. Weitere Informationen finden Sie unter [Außerbetriebsetzen und Deaktivieren von Azure Rights Management](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md).

Bevor Sie Ihre Azure RMS-Bereitstellung außer Betrieb setzen, würden wir jedoch gerne erfahren bzw. verstehen, warum Sie diese Entscheidung getroffen haben. Wenn Azure RMS Ihren geschäftlichen Anforderungen nicht gerecht wird, können Sie Kontakt mit uns aufnehmen, um zu erfahren, ob in naher Zukunft neue Funktionen geplant oder ob Alternativen verfügbar sind. Senden Sie eine E-Mail-Nachricht an [AskIPTeam@Microsoft.com](mailto:askipteam@microsoft.com?subject=Planning%20to%20decommission%20Azure%20RMS). Wir freuen uns darauf, Ihre technischen und geschäftlichen Anforderungen mit Ihnen zu besprechen.

## Kann ich steuern, welche Benutzer Azure RMS verwenden können, um Inhalte zu schützen?
Ja, hat Azure RMS hat hierfür Steuerelemente zum Einbinden (Onboarding) von Benutzern. Weitere Informationen finden Sie im Abschnitt [Konfigurieren von Onboarding-Steuerelementen für eine stufenweise Bereitstellung](../Topic/Activating_Azure_Rights_Management.md#BKMK_OnboardingControls) des Themas [Aktivieren von Azure Rights Management](../Topic/Activating_Azure_Rights_Management.md).

## Kann ich verhindern, dass Benutzer geschützte Dokumente für bestimmte Organisationen freigeben?
Einer der größten Vorteile von Azure RMS besteht darin, dass es B2B-Zusammenarbeit unterstützt, ohne dass Sie explizite Vertrauensstellungen für jede Partnerorganisation konfigurieren müssen, denn Azure AD übernimmt die Authentifizierung für Sie.

Es gibt keine Verwaltungsoption, mit der verhindert werden kann, dass Benutzer Dokumente geschützt für bestimmte Organisationen freigeben. Angenommen, Sie möchten eine Organisation blockieren, der Sie nicht vertrauen oder die ein konkurrierendes Unternehmen hat. Azure RMS daran zu hindern, geschützte Dokumente an Benutzer in dieser Organisationen zu senden, wäre nicht sinnvoll, da Benutzer ihre Dokumente dann ungeschützt freigeben würden, und dies ist wahrscheinlich genau das, was in diesem Szenario nicht geschehen soll! Beispielsweise könnten Sie nicht erkennen, wer vertrauliche Unternehmensdokumente für welche Benutzer in dieser Organisation freigibt, wogegen Sie dies erkennen können, wenn das Dokument (oder die E-Mail) durch Azure RMS geschützt wird.

## Wenn ich ein geschütztes Dokument für eine Person außerhalb meiner Firma freigebe, wie wird dieser Benutzer authentifiziert?
Azure RMS verwendet immer ein Azure Active Directory-Konto und eine zugeordnete E-Mail-Adresse für die Benutzerauthentifizierung, wodurch sich eine nahtlose Business-to-Business-Zusammenarbeit für Administratoren ergibt. Wenn die andere Organisation Azure-Dienste verwendet, haben Benutzer bereits Konten in Azure Active Directory, selbst wenn diese Konten lokal erstellt und verwaltet und dann mit Azure synchronisiert werden.  Wird in der Organisation Office 365 verwendet, verwendet dieser Dienst (im Hintergrund) ebenfalls Azure Active Directory für die Benutzerkonten.  Wenn die Organisation des Benutzers keine verwalteten Konten in Azure hat, können sich Benutzer für [RMS for Individuals](https://technet.microsoft.com/library/dn592127.aspx) registrieren. Dadurch werden ein nicht verwalteter Azure-Mandant und ein Verzeichnis für die Organisation mit einem Konto für den Benutzer erstellt, sodass dieser Benutzer dann für Azure RMS authentifiziert werden kann.

Die Authentifizierungsmethode für diese Konten kann unterschiedlich sein, je nachdem, wie der Administrator in der anderen Organisation die Azure Active Directory-Konten konfiguriert hat. Beispielsweise können Kennwörter, die für diese Konten erstellt wurden, Multi-Factor Authentication (MFA, mehrstufige Authentifizierung), Verbund oder Kennwörter verwendet werden, die in Active Directory-Domänendienste erstellt und dann mit Azure Active Directory synchronisiert wurden.

## Kann ich Benutzer, die nicht zu meinem Unternehmen gehören, zu benutzerdefinierten Vorlagen hinzufügen?
Ja.  Ein Erstellen von benutzerdefinierten Vorlagen, die Endbenutzer (und Administratoren) in Anwendungen auswählen können, ermöglicht es Benutzern, schnell und problemlos Informationsschutz anzuwenden, indem sie vordefinierte Richtlinien verwenden, die Sie definiert haben. Eine der Einstellungen in der Vorlage bestimmt, wer auf den Inhalt zugreifen kann, und Sie können Benutzer und Gruppen aus Ihrer Organisation sowie Benutzer angeben, die nicht zu Ihrer Organisation gehören.

Um Benutzer anzugeben, die nicht zu Ihrer Organisation gehören, verwenden Sie das [Windows PowerShell-Modul für Azure Rights Management](https://technet.microsoft.com/library/jj585012.aspx):

-   **Erstellen oder Aktualisieren der Vorlage mithilfe eines Rechtedefinitionsobjekts**.    Geben Sie die externen E-Mail-Adressen und ihre Rechte in einem Rechtedefinitionsobjekt an, das Sie dann zum Erstellen oder Aktualisieren einer Vorlage verwenden. Sie geben das Rechtedefinitionsobjekt an, indem Sie mit dem [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx)-Cmdlet eine Variable erstellen und diese Variable anschließend mit dem [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx)-Cmdlet (für eine neue Vorlage) oder mit dem [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx)-Cmdlet (zum Ändern einer vorhandenen Vorlage) für den -RightsDefinition-Parameter bereitstellen. Wenn Sie jedoch diese Benutzer zu einer vorhandenen Vorlage hinzufügen, müssen Sie nicht nur für die externen Benutzer Rechtedefinitionsobjekte definieren, sondern auch für die vorhandenen Gruppen in den Vorlagen.

Weitere Informationen zu benutzerdefinierten Vorlagen finden Sie unter [Konfigurieren benutzerdefinierter Vorlagen für Azure Rights Management](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md).

## Welche Geräte und welche Dateitypen werden von Azure RMS unterstützt?
Eine Liste der unterstützten Geräte finden Sie im Abschnitt [Clientgeräte, die Azure RMS unterstützen](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedDevices) des Themas [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md). Da derzeit nicht alle unterstützten Geräte alle RMS-Funktionen unterstützen, sehen Sie sich auch die [Clientgerätefunktionen](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_ClientCapabilities)-Tabelle im gleichen Thema an.

Azure RMS kann alle Dateitypen unterstützen. Für Text-, Bild-, Microsoft Office-Dateien (Word, Excel, PowerPoint), PDF-Dateien und einige andere Anwendungsdateitypen stellt Azure RMS systemeigenen Schutz bereit, der Verschlüsselung und die Durchsetzung von Rechten (Berechtigungen) umfasst. Für alle anderen Anwendungen und Dateitypen bietet generischer Schutz Dateiverkapselung und Authentifizierung, damit überprüft wird, ob ein Benutzer zum Öffnen der Datei autorisiert ist.

Eine Liste der Dateinamenerweiterungen, für die Azure RMS systemeigene Unterstützung bietet, finden Sie im Abschnitt [Unterstützte Dateitypen und Dateinamenerweiterungen](http://technet.microsoft.com/library/dn339003.aspx) des [Administratorhandbuchs der Rights Management-Freigabeanwendung](http://technet.microsoft.com/library/dn339003.aspx). Nicht aufgeführte Dateinamenerweiterungen werden mithilfe der RMS-Freigabeanwendung unterstützt, die automatisch generischen Schutz auf diese Dateien anwendet.

## Ab wann wird Migration von AD RMS unterstützt?
Zunächst hat Azure RMS Migration von einer lokalen Bereitstellung von Rights Management, z. B. AD RMS, nicht unterstützt. Eine solche Migration wird aber jetzt unterstützt.

Weitere Informationen finden Sie unter [Migration von AD RMS zu Azure Rights Management](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md).

## Wir möchten BYOK mit Azure RMS verwenden, haben jedoch erfahren, dass diese Kombination nicht mit Exchange Online kompatibel ist. Wie lautet Ihre Empfehlung?
Lassen Sie sich durch diese aktuelle Einschränkung nicht von der Azure RMS-Bereitstellung abbringen. Wenn Sie Exchange Online verwenden und BYOK (Bring Your Own Key) nutzen möchten, empfehlen wir, dass Sie Azure RMS im Standard-Schlüsselverwaltungsmodus bereitstellen, in dem Microsoft Ihren Schlüssel generiert und verwaltet. Auf diese Weise erhalten Sie jetzt alle Vorteile bezüglich des Schutzes wichtiger Dateien und E-Mails mit der Option, zu einem späteren Zeitpunkt zu BYOK zu wechseln (z. B. wenn Exchange Online BYOK unterstützt).

Wenn Ihre Unternehmensrichtlinien jedoch erfordern, dass Sie ein Hardwaresicherheitsmodul (HSM) verwenden, und dies würde Ihre Azure RMS-Bereitstellung blockieren, können Sie alternativ jetzt Azure RMS mit BYOK bereitstellen, mit verminderter RMS-Funktionalität für Exchange. Weitere Informationen finden Sie im Abschnitt [BYOK – Preise und Einschränkungen](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_Pricing) des Themas [Planen und Implementieren Ihres Azure Rights Management-Mandantenschlüssels](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md).

## Eine Funktion, die ich suche, scheint nicht mit SharePoint-geschützten Bibliotheken zu funktionieren – ist die Unterstützung dieser Funktion geplant?
Derzeit unterstützt SharePoint RMS-geschützte Dokumente durch Verwenden von IRM-geschützten Bibliotheken, die weder benutzerdefinierte Vorlagen, noch Dokumentnachverfolgung noch einige andere Funktionen unterstützen.  Weitere Informationen finden Sie, wenn Sie den Abschnitt [SharePoint Online und OneDrive for Business: IRM-Konfiguration](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharePointOnline) im Thema [Unterstützung von Azure Rights Management durch Anwendungen](../Topic/How_Applications_Support_Azure_Rights_Management.md) erweitern.

Wenn Sie an einer bestimmten Funktion interessiert sind, die noch nicht unterstützt wird, sollten Sie die Ankündigungen im [RMS Team Blog](http://blogs.technet.com/b/rms/) verfolgen.

## Wie konfiguriere ich OneDrive for Business in SharePoint Online, sodass Benutzer ihre Dateien sicher für Personen innerhalb und außerhalb des Unternehmens freigeben können?
Als Office 365-Administrator konfigurieren Sie dies normalerweise nicht. Eine solche Konfiguration erfolgt durch Benutzer.

Als SharePoint-Websiteadministrator aktivieren und konfigurieren Sie IRM für eine SharePoint-Bibliothek, deren Besitzer Sie sind. OneDrive for Business ist so konzipiert, dass die Benutzer IRM für ihre eigene OneDrive for Business-Bibliothek aktivieren und konfigurieren.  Mithilfe von PowerShell können Sie das jedoch für sie übernehmen. Anweisungen dazu finden Sie im Artikel [Konfigurieren von Anwendungen für Azure Rights Management](../Topic/Configuring_Applications_for_Azure_Rights_Management.md), wenn Sie den Abschnitt [SharePoint Online und OneDrive for Business: IRM-Konfiguration](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharePointOnline) erweitern.

## Gibt es besondere Tipps und Tricks für eine erfolgreiche RMS-Bereitstellung?
Nachdem wir viele Bereitstellungen begleitet und uns mit Kunden, Partnern, Beratern und Supportmitarbeitern unterhalten haben – ist das einer der größten Tipps, die wir aus unserer Erfahrung weitergeben können: **Entwerfen Sie einfache Rechterichtlinien, und stellen Sie sie entsprechend bereit**.

Da Azure RMS sichere Freigaben mit praktisch jedermann unterstützt, können Sie bei der Reichweite Ihres Informationsschutzes Ehrgeiz entwickeln. Seien Sie aber konservativ bei Ihren Rechterichtlinien. Für die meisten Organisationen hat die Vermeidung von Datenlecks durch Anwenden der standardmäßigen Rechterichtlinienvorlage, die den Zugriff auf Personen in der eigenen Organisation einschränkt, die größte geschäftliche Bedeutung. Natürlich können Sie Rechte, wenn nötig, viel kleinteiliger festlegen – etwa indem Sie Personen am Drucken, Bearbeiten usw. hindern. Behandeln Sie die kleinteiligeren Einschränkungen jedoch als Ausnahme für Dokumente, die wirklich hohe Sicherheitsstufen benötigen, und implementieren Sie diese restriktiveren Richtlinien nicht am ersten Tag, sondern gehen Sie eher stufenweise vor.

## Welche Features können mit verschiedenen Abonnements für Azure RMS verwendet werden?
Bei kostenpflichtigen Abonnements, die Azure RMS unterstützen (Office 365, Azure RMS Premium und Enterprise Mobility Suite), gibt es hinsichtlich der unterstützten RMS-Features einige Unterschiede. Eine Liste dieser Funktionen finden Sie unter [Vergleich der Rights Management Services(RMS)-Angebote](http://technet.microsoft.com/dn858608).

Das kostenlose Abonnement, das Azure RMS unterstützt (RMS for Individuals), unterstützt das Nutzen von Inhalten, die durch die Azure RMS geschützt sind. Weitere Informationen finden Sie unter [RMS for Individuals und Azure Rights Management](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md).

## Wo kann ich technische Informationen über das kostenlose Azure RMS-Abonnement (RMS for Individuals) erhalten – um beispielsweise Informationen über die tatsächliche Funktionsweise, die Steuerung der Konten und Domänen zu erhalten, die nicht verwendet werden können?
Die Antworten auf diese Fragen finden Sie im Thema [RMS for Individuals und Azure Rights Management](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md).

## Wie erhalten wir erneut Zugriff auf Dateien, die von einem Mitarbeiter geschützt wurden, der die Organisation verlassen hat?
Verwenden Sie die Administratorfunktion von Azure RMS, über die autorisierte Benutzer volle Besitzerrechte für alle Nutzungslizenzen erhalten, die vom RMS-Mandanten Ihrer Organisation gewährt wurden. Dieselbe Funktion ermöglicht darüber hinaus autorisierten Diensten ggf. die Indizierung und Inspektion von Dateien.

Weitere Informationen finden Sie unter [Konfigurieren von Administratoren für Azure Rights Management und Discovery Services oder die Datenwiederherstellung](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md).

## Kann Rights Management Bildschirmaufnahmen verhindern?
Rights Management blockiert Bildschirmaufnahmen bzw. das Erstellen von Screenshots in den am häufigsten dafür verwendeten Tools. Dies kann helfen, die versehentliche oder nachlässige Offenlegung vertraulicher oder sensibler Informationen zu verhindern. Es gibt jedoch viele Möglichkeiten, wie Benutzer die auf dem Bildschirm angezeigten Daten weitergeben können. Das Erstellen von Screenshots ist nur eine davon. Beispielsweise kann ein Benutzer, der die angezeigten Informationen vorsätzlich weitergeben möchte, sie mit der Kamera seines Handys abfotografieren, sie abtippen oder einfach mündlich einer anderen Person mitteilen.

Diese Beispiele zeigen: Technologie kann nicht immer verhindern, dass Benutzer unerlaubt Daten und Informationen weitergeben. Rights Management kann zwar helfen, Ihre wichtigen Daten mithilfe von Autorisierungen und Nutzungsrichtlinien zu schützen. Aber Sie sollten diese Lösung für die Rechteverwaltung im Unternehmen durch andere Kontrollmaßnahmen ergänzen. Arbeiten Sie z. B. mit physischen Sicherheitskontrollen, prüfen und überwachen Sie die Mitarbeiter, die zum Zugriff auf Unternehmens- oder Organisationsdaten autorisiert sind, und investieren Sie in Benutzerschulungen, damit die Benutzer verstehen, welche Daten nicht weitergegeben oder geteilt werden dürfen.

## Wo finde ich weitere Informationen zur Azure RMS – wie z. B. rechtliche Hinweise, Informationen zur Kompatibilität und SLAs?
Azure RMS unterstützt weitere Dienste und verwendet zusätzliche Dienste. Wenn Sie Informationen zur Azure RMS suchen, jedoch nicht zur Verwendung des Azure RMS-Diensts, sehen Sie sich folgende Ressourcen an:

**Rechtliche Hinweise und Datenschutz:**

-   Informationen zur Microsoft Azure-Vereinbarung: [Microsoft Azure-Vereinbarung](http://azure.microsoft.com/support/legal/subscription-agreement/)

-   Informationen zum Microsoft Azure-Datenschutz: [Datenschutzerklärung zu Microsoft Azure](http://azure.microsoft.com/support/legal/privacy-statement/)

**Sicherheit, Compliance und Überwachung:**

Siehe den Abschnitt [Sicherheits-, Compliance- und gesetzliche Anforderungen](../Topic/What_is_Azure_Rights_Management_.md#BKMK_RMScompliance) im Thema [Was ist Azure Rights Management?](../Topic/What_is_Azure_Rights_Management_.md). Zusätzlich:

-   Informationen zu externen Zertifizierungen für Azure RMS: [Microsoft Azure Trust Center](http://azure.microsoft.com/support/trust-center/)

-   FIPS 140-Informationen: [FIPS 140-Überprüfung](https://technet.microsoft.com/library/security/cc750357.aspx)

**Vereinbarungen zum Servicelevel:**

-   Vereinbarung zum Servicelevel für Azure RMS, ausgewählt nach Land: [Vereinbarung zum Servicelevel](http://microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)

-   Vereinbarung zum Servicelevel für Azure Active Directory: [Vereinbarungen zum Servicelevel](http://azure.microsoft.com/support/legal/sla/)

**Dokumentation:**

-   Azure Active Directory-Dokumentationswebsite: [Azure Active Directory](http://azure.microsoft.com/documentation/services/active-directory/)

-   Azure Active Directory-Bibliothek: [Azure Active Directory](http://msdn.microsoft.com/library/azure/jj673460.aspx)

-   Office 365-Bibliothek: [Office 365](http://technet.microsoft.com/library/dn127064%28v=office.14%29.aspx)

## Wie gehe ich vor, wenn meine Frage hier nicht behandelt wird?
Verwenden Sie die Links und Ressourcen, die unter [Informationen zu und Unterstützung für Azure Rights Management](../Topic/Information_and_Support_for_Azure_Rights_Management.md) aufgeführt werden.

Darüber hinaus gibt es häufig gestellte Fragen (FAQs) für Endbenutzer:

-   [Häufig gestellte Fragen zur Rights Management-Freigabeanwendung für Windows](https://technet.microsoft.com/dn467883)

-   [Häufig gestellte Fragen (FAQ) zur Rights Management-Freigabeanwendung für mobile und für Mac-Plattformen](https://technet.microsoft.com/dn451248)

-   [Häufig gestellte Fragen zur Dokumentenverfolgung](http://go.microsoft.com/fwlink/?LinkId=523977)

Diese FAQ-Seite wird regelmäßig aktualisiert. Dabei werden die neuen Beiträge in den Ankündigungen zu den monatlichen Dokumentationsaktualisierungen im Blog des [RMS-Teams (Microsoft Rights Management)](http://blogs.technet.com/b/rms/) aufgelistet.

> [!TIP]
> Sie können das [docs-Tag](http://blogs.technet.com/b/rms/archive/tags/docs/) im Blog verwenden, um diese Dokumentationsankündigungen leichter zu finden.

## Siehe auch
[Erste Schritte mit Azure Rights Management](../Topic/Getting_Started_with_Azure_Rights_Management.md)


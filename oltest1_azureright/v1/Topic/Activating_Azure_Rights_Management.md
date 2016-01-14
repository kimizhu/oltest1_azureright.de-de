---
description: na
keywords: na
title: Activating Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f8707e01-b239-4d1a-a1ea-0d1cf9a8d214
---
# Aktivieren von Azure Rights Management
Wenn Sie [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS) aktivieren, kann Ihre Organisation damit beginnen, wichtige Daten mithilfe von Anwendungen und Diensten zu schützen, die diese Informationschutzlösung unterstützen. Administratoren können außerdem geschützte Dateien und E-Mails, die Ihrer Organisation gehören, verwalten und überwachen. Sie müssen [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] aktivieren, bevor Sie beginnen können, IRM-Features (Information Rights Management) in Office, SharePoint und Exchange zu verwenden und sensible oder vertrauliche Dateien zu schützen.

Wenn Sie weitere Informationen zu Azure Rights Management benötigen, bevor Sie den Dienst aktivieren (Beispiel: welche geschäftlichen Probleme gelöst werden, einige typische Anwendungsfälle sowie Informationen zur Funktionsweise) lesen Sie [Was ist Azure Rights Management?](../Topic/What_is_Azure_Rights_Management_.md).

> [!IMPORTANT]
> Bevor Sie [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] aktivieren, sollten Sie sicherstellen, dass Ihre Organisation einen Serviceplan hat, der [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]-Dienste beinhaltet. Ist dies nicht der Fall, können Sie Azure RMS nicht aktivieren.
> 
> Weitere Informationen finden Sie im Thema [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md) im Abschnitt [Cloud-Abonnements, die Azure RMS unterstützen](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions).

Nachdem Sie Azure RMS aktiviert haben, können alle Benutzer in Ihrer Organisation Information Protection (Informationsschutz) auf die eigenen Dateien anwenden und Dateien öffnen (nutzen), die über Azure RMS geschützt wurden. Bei Bedarf können Sie jedoch einschränken, wer Informationsschutz anwenden kann, indem Sie Onboardingsteuerungsrichtlinien für eine in Phasen vorgenommene Bereitstellung verwenden. Weitere Informationen finden Sie in diesem Thema im Abschnitt [Konfigurieren von Onboarding-Steuerelementen für eine stufenweise Bereitstellung](../Topic/Activating_Azure_Rights_Management.md#BKMK_OnboardingControls).

## Aktivieren von Rights Management
Verwenden Sie eins der folgenden Verfahren, um [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] zu aktivieren.

> [!TIP]
> Sie können auch das Windows PowerShell-Cmdlet [Enable-Aadrm](http://msdn.microsoft.com/library/windowsazure/dn629412.aspx) zur Aktivierung von [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] nutzen.

#### So aktivieren Sie Rights Management über das Office 365 Admin Center

1.  Nachdem Sie sich für einen Office 365-Plan angemeldet haben, der Rights Management umfasst, [melden Sie sich bei Office 365 mit Ihrem Arbeits- oder Schulkonto an](https://portal.office.com/), das als Administrator für die Office 365-Bereitstellung fungiert.

2.  Wenn das Office 365 Admin Center nicht automatisch angezeigt wird, wählen Sie in der linken oberen Ecke das Symbol für das App-Startprogramm aus, und wählen Sie dann **Administrator** aus. Die Kachel **Administrator** wird nur für Office 365-Administratoren angezeigt.

    > [!TIP]
    > Hilfe zum Admin Center finden Sie in [Informationen zum Office 365 Admin Center - Hilfe für Administratoren](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547).

3.  Klicken Sie im linken Bereich auf **DIENSTEINSTELLUNGEN**.

4.  Klicken Sie auf **Azure Rights Management**.

    > [!NOTE]
    > Wenn diese Option nicht angezeigt wird, kann dies daran liegen, dass Ihr Serviceplan oder Ihre Produktversion Rights Management nicht unterstützen kann, oder dass noch kein Upgrade für die Unterstützung von Rights Management durchgeführt wurde.
    > 
    > Verwenden Sie die Informationen im Abschnitt [Cloud-Abonnements, die Azure RMS unterstützen](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) des Themas [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md), um Ihre Unterstützung zu überprüfen. Wenn Ihr Serviceplan oder Ihre Produktversion unterstützt wird, aber die Rights Management-Option nicht angezeigt wird, kann dies daran liegen, dass noch kein Upgrade des Diensts erfolgt ist. Wenn Sie Hilfe zu diesem Problem benötigen, senden Sie eine E-Mail-Nachricht an das [Askipteam](mailto:askipteam@microsoft.com?subject=I%20cannot%20activate%20RMS).

5.  Klicken Sie auf der Seite **RIGHTS MANAGEMENT** auf **Verwalten**.

6.  Klicken Sie auf der Seite **Rights Management** auf **Aktivieren**.

7.  Klicken Sie, wenn Sie gefragt werden **Möchten Sie die Rechteverwaltung aktivieren?** auf **Aktivieren**.

Es sollten jetzt **Rights Management ist aktiviert** und die Option zum Deaktivieren angezeigt werden.

#### So aktivieren Sie Rights Management über das klassische Azure-Portal

1.  Nachdem Sie sich für Ihr Azure-Konto registriert haben, [melden Sie sich am klassischen Azure-Portal an](http://go.microsoft.com/fwlink/p/?LinkID=275081).

2.  Klicken Sie im linken Bereich auf **ACTIVE DIRECTORY**.

3.  Klicken Sie auf der Seite **Active Directory** auf **RIGHTS MANAGEMENT**.

4.  Wählen Sie das Verzeichnis aus, für das Sie [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] verwalten möchten, klicken Sie auf **AKTIVIEREN**, und bestätigen Sie Ihre Aktion.

    > [!NOTE]
    > Wenn ein Aktivierungsfehler angezeigt wird, kann das die Ursache haben, dass Ihr Serviceplan oder Ihre Produktversion keine Unterstützung für [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] bietet.
    > 
    > Verwenden Sie die Informationen im Abschnitt [Cloud-Abonnements, die Azure RMS unterstützen](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) des Themas [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md), um Ihre RMS-Unterstützung zu überprüfen. Wenn Sie Hilfe zu diesem Problem benötigen, senden Sie eine E-Mail-Nachricht an das [Askipteam](mailto:askipteam?subject=I%20cannot%20activate%20RMS).

Der **RECHTEVERWALTUNGSSTATUS** sollte nun **Aktiv** anzeigen, und die Option **AKTIVIEREN** wird durch **DEAKTIVIEREN** ersetzt.

### Rights Management-Statuswerte und -Beschreibungen im klassischen Azure-Portal
Zusätzlich zum Status **Aktiv**, der angibt, dass der Rights Management-Dienst aktiviert und einsatzbereit ist, wird darüber hinaus möglicherweise **Inaktiv**, **Nicht verfügbar** oder **Nicht autorisiert** angezeigt.

|Statuswert|Beschreibung|
|--------------|----------------|
|**Aktiv**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] ist aktiviert und kann verwendet werden.|
|**Inaktiv**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] ist deaktiviert und muss aktiviert werden, bevor Ihre Organisation Dateien schützen kann.|
|**Nicht verfügbar**|Der [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] Service ist nicht verfügbar. Versuchen Sie es später erneut.|
|**Nicht autorisiert**|Sie sind nicht berechtigt, den Status des [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] Services anzuzeigen. Ihr Konto ist z. B. gesperrt, oder Sie sind nicht der globale Administrator für den ausgewählten Mandanten.|

## <a name="BKMK_OnboardingControls"></a>Konfigurieren von Onboarding-Steuerelementen für eine stufenweise Bereitstellung
Sollen nicht alle Benutzer sofort die Möglichkeit haben, Dateien mithilfe von Azure RMS zu schützen, können Sie mit dem Windows PowerShell-Befehl [Set-AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857521.aspx) Benutzereinbindungsrichtlinien (Onboardingsteuerungsrichtlinien) konfigurieren. Sie können diesen Befehl ausführen, bevor oder nachdem Sie Azure RMS aktivieren.

> [!IMPORTANT]
> Damit Sie diesen Befehl verwenden können, benötigen Sie mindestens Version **2.1.0.0** des [Azure RMS Windows PowerShell-Moduls](http://go.microsoft.com/fwlink/?LinkId=257721).
> 
> Um die installierte Version zu überprüfen, führen Sie Folgendes aus: **(Get-Module aadrm –ListAvailable).Version**

Wenn Sie beispielsweise möchten, dass zunächst nur Administratoren der Gruppe "IT-Abteilung" (die die Objekt-ID "fbb99ded-32a0-45f1-b038-38b519009503" hat) in der Lage sein sollen, Inhalte zu Testzwecken zu schützen, verwenden Sie den folgenden Befehl:

```
Set-AadrmOnboardingControlPolicy – SecurityGroupObjectId fbb99ded-32a0-45f1-b038-38b519009503
```
Beachten Sie, dass Sie für diese Konfigurationsoption eine Gruppe angeben müssen. Sie können keine einzelnen Benutzer angeben.

Oder Sie möchten sicherstellen, dass nur Benutzer, die ordnungsgemäß für die Verwendung von Azure RMS lizenziert sind, Inhalte schützen können:

```
Set-AadrmOnboardingControlPolicy -UseRmsUserLicense $true
```
Wenn Sie diese Onboarding-Steuerelemente verwenden, können alle Benutzer in der Organisation immer geschützte Inhalte nutzen, die durch Ihre Teilmenge von Benutzern geschützt wurde, können aber Informationsschutz aus Clientanwendungen nicht selbst anwenden. Beispielsweise sehen sie nicht die Standardvorlagen in ihren Office-Clients, die automatisch veröffentlicht werden, wenn Azure RMS aktiviert ist, oder benutzerdefinierte Vorlagen, die Sie ggf. konfiguriert haben.  Serverseitige Anwendung wie z. B. Exchange können eigene Steuerelemente pro Benutzer für die RMS-Integration implementieren, um das gleiche Ergebnis zu erzielen.

## Nächste Schritte
Nachdem Sie jetzt [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] für Ihre Organisation aktiviert haben, verwenden Sie die [Roadmap für die Bereitstellung von Azure Rights Management](../Topic/Azure_Rights_Management_Deployment_Roadmap.md), um herauszufinden, ob Sie vor dem Rollout von [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] für Benutzer und Administratoren ggf. weitere Konfigurationsschritte ausführen müssen. Angenommen, Sie möchten [benutzerdefinierte Vorlagen](http://technet.microsoft.com/library/dn642472.aspx) verwenden, um es den Benutzern zu erleichtern, Informationsschutz auf Dateien anzuwenden, Ihre lokalen Server durch Installation des [RMS-Verbindungsdiensts](http://technet.microsoft.com/library/dn375964.aspx) für die Verwendung von [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] zu verbinden, und die [Rights Management-Freigabeanwendung](http://technet.microsoft.com/library/jj585031.aspx) bereitzustellen, die den Schutz aller Dateitypen auf allen Geräten unterstützt. Office-Dienste (z. B. Exchange Online und SharePoint Online) erfordern zusätzliche Konfigurationsschritte, bevor Sie ihre IRM-Features (Information Rights Management) verwenden können. Wenn jedoch keine weiteren Konfigurationsschritte ausgeführt werden müssen, lesen Sie [Verwenden von Azure Rights Management](../Topic/Using_Azure_Rights_Management.md), um Hilfestellung zum Betrieb zu erhalten, damit eine erfolgreiche Bereitstellung für Ihre Organisation unterstützt wird.

Weitere Informationen dazu, wie Ihre Anwendungen in Verbindung mit [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] funktionieren, finden Sie unter [Unterstützung von Azure Rights Management durch Anwendungen](../Topic/How_Applications_Support_Azure_Rights_Management.md).

## Siehe auch
[Konfigurieren von Azure Rights Management](../Topic/Configuring_Azure_Rights_Management.md)


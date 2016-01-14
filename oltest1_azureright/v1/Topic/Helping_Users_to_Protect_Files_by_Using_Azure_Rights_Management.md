---
description: na
keywords: na
title: Helping Users to Protect Files by Using Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 58f9a6ff-4121-4c8c-9865-1bb290604ad2
---
# Unterst&#252;tzung von Benutzern beim Sch&#252;tzen von Dateien unter Verwendung von Azure Rights Management
Nachdem Sie Azure Rights Management (Azure RMS) für Ihre Organisation bereitgestellt haben, bieten Sie Ihren Benutzern, Administratoren und Ihrem Helpdesk Hilfe und Anleitung:

-   **Endbenutzerinformationen:**

    Informieren Sie Benutzer darüber, wie und wann sie Dokumente und E-Mails, die sensible Informationen enthalten, schützen können. Stellen Sie diese Informationen wann immer möglich für ihre vorhandenen Workflows bereit, sodass sie die zusätzlichen Schritte in einen bereits vertrauten Prozess implementieren können, anstatt völlig neue Prozesse einzuführen. Stellen Sie sicher, dass sie die Vorteile (und Risiken) kennenlernen, die für Ihr Geschäft spezifisch sind, und bieten Sie Ihnen Anleitung, wann Dateien und E-Mails geschützt werden sollten. Wenn Sie [benutzerdefinierte Vorlagen](http://technet.microsoft.com/library/dn642472.aspx) konfiguriert haben, bieten Sie Anleitungen dazu, welche auszuwählen sind, wenn der Vorlagenname und die Beschreibung nicht aussagekräftig genug sind, um die richtige auszuwählen.

    > [!TIP]
    > Beispielvideos für Endbenutzer:
    > 
    > -   [Azure RMS-Benutzererfahrung](http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-user-experience)
    > -   [Azure RMS-Dokumentenverfolgung und -widerruf](http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation)

-   **Administratorinformationen:**

    Einige Anwendungen wenden automatisch Informationsschutz an, indem sie Richtlinien und Einstellungen verwenden, die von Administratoren konfiguriert werden. Für diese Anwendungen müssen Sie möglicherweise Anleitungen für andere Administratoren bereitstellen, die diese Anwendungen und Dienste verwalten. Weitere Informationen finden Sie unter [Unterstützung von Azure Rights Management durch Anwendungen](../Topic/How_Applications_Support_Azure_Rights_Management.md) und [Konfigurieren von Anwendungen für Azure Rights Management](../Topic/Configuring_Applications_for_Azure_Rights_Management.md).

-   **Helpdesk-Informationen:**

    Eines der nützlichsten Helpdesktools ist der [RMS Analyzer](https://www.microsoft.com/en-us/download/details.aspx?id=46437).   Helpdesk-Operatoren können das Tool mit der Azure RMS-Administratoroption ausführen und Benutzer dazu auffordern, es mit der Azure RMS-Benutzeroption auszuführen. Dieses Tool unterstützt Sie nicht nur bei der Fehlersuche, sondern behebt gefundene Probleme und zeichnet, sofern der Fehler nicht behoben werden konnte, Ablaufverfolgungsprotokolle auf.

    Stellen Sie bei legitimen Anfragen für den Vollzugriff auf geschützte Dokumente – z. B. eine Anfrage von der Rechtsabteilung oder einem Vorgesetzten, nachdem ein Mitarbeiter die Organisation verlassen hat – sicher, dass das Helpdesk über Prozesse verfügt, dies durch Verwendung des Azure RMS-[Administratorfunktion](https://technet.microsoft.com/en-us/library/mt147272.aspx) anzufordern.

    Darüber hinaus finden Sie im Folgenden einige der möglicherweise auftretenden Probleme:

    -   **Hilfe bei der Anmeldung:**

        Benutzer werden möglicherweise zur Eingaben von Anmeldeinformationen aufgefordert, wenn Azure RMS einen Benutzer authentifizieren muss und dazu keine zwischengespeicherten Anmeldeinformationen verwenden kann. Dies ist dann das Geschäfts- oder Schulkonto des Benutzers, das Ihrem Office 365- oder Azure Active Directory-Mandanten zugeordnet ist. Es ist kein Microsoft-Konto (früher Microsoft Live ID) oder ein persönliches E-Mail-Konto des Benutzers, weil diese zurzeit von Azure RMS nicht unterstützt werden. Stellen Sie Benutzern und Ihrem Helpdesk Anleitungen bereit, welches Konto zu verwenden ist, wenn bei Verwendung dieser Anwendungen mit Azure RMS Anmeldeinformationen abgefragt werden.

    -   **Probleme beim Schützen oder Nutzen von Inhalten:**

        Stellen Sie sicher, dass den Benutzern entsprechende Anweisungen für die von ihnen verwendeten Anwendungen vorliegen und dass sie Anwendungen und Geräte verwenden, die von Azure RMS unterstützt werden. Weitere Informationen zu unterstützten Anwendungen und Geräten finden Sie unter [Voraussetzungen für Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md).

        Wenn Benutzern beim Versuch, Inhalte zu schützen oder zu öffnen, eine Fehlermeldung angezeigt wird, fordern Sie sie auf, den [RMS Analyzer](https://www.microsoft.com/en-us/download/details.aspx?id=46437) als Azure RMS-Benutzer auszuführen.

        Wenn Benutzer melden, dass sie geschützte Inhalte zwar öffnen können, jedoch nicht über die erforderlichen Berechtigungen verfügen, fordern Sie sie dazu auf, den [RMS Analyzer](https://www.microsoft.com/en-us/download/details.aspx?id=46437) als Azure RMS-Benutzer auszuführen und die Vorlagen herunterzuladen und anzuzeigen. Hierdurch wird bestätigt, dass sie die Vorlagen erfolgreich heruntergeladen haben und welche Rechte die Vorlage bereitstellt. Die Ursache hierfür könnte sein, dass sich der Benutzer nicht in der Gruppe befindet, die für die Vorlage konfiguriert wurde, oder dass die Vorlage für den Benutzer neu konfiguriert werden muss.

Verwenden Sie folgende Abschnitte für anwendungsspezifische Informationen, um Benutzern beim Schützen sensibler Dokumente und E-Mails zu helfen.

## Verwenden von Informationsschutz mit der Rights Management-Freigabeanwendung
Die Rights Management (RMS)-Freigabeanwendung ist für Benutzer erforderlich, damit diese Inhalte schützen und geschützte Inhalte benutzen können, wenn sie Office 2010 verwenden, wird aber auch für alle Computer und mobilen Geräte empfohlen, die Azure RMS unterstützen.

Die RMS-Freigabeanwendung erleichtert es Benutzern, wichtige Dokumente zu schützen, die von ihnen geschützten Dokumente nachzuverfolgen und, falls nötig, den Zugriff darauf zu widerrufen.

Anweisungen zur Verwendung dieser Anwendung für Windows-Computer finden Sie im [Benutzerhandbuch der Rights Management-Freigabeanwendung](http://technet.microsoft.com/library/dn339006.aspx).

Informationen für mobile Geräte finden Sie unter [Häufig gestellte Fragen (FAQ) zur Rights Management-Freigabeanwendung für mobile Plattformen](http://technet.microsoft.com/dn451248).

> [!TIP]
> Ein allgemeines Beispielszenario mit Screenshots finden Sie im Abschnitt [Sicheres Freigeben von Anlagen für mobile Benutzer](../Topic/What_is_Azure_Rights_Management_.md#BKMK_Example_SharingApp) im Thema [Was ist Azure Rights Management?](../Topic/What_is_Azure_Rights_Management_.md).

## Verwenden von Informationsschutz mit Office 365, Office 2016 oder Office 2013
Wenn Sie Azure RMS verwenden, ohne die Rights Management-Freigabeanwendung installiert zu haben, wird Benutzern weder im Menüband die Schaltfläche **Geschützt freigeben** noch im Datei-Explorer **Direkt schützen** angezeigt, wodurch das Schützen von Dateien erleichtert würde. Diese Benutzer müssen ähnliche Anleitungen wie diese befolgen.

> [!TIP]
> Um anwendungsspezifische Hilfe und Anleitungen zur Verwendung des Informationsschutzes mit diesen Anwendungen zu finden, suchen Sie nach **IRM** sowie dem Anwendungsnamen und der -version.

#### So schützten Sie ein Dokument in Word 2013

1.  Erstellen Sie in Microsoft Word ein neues Dokument.

2.  Klicken Sie im Menü **Datei** auf **Info**, **Dokument schützen**, **Zugriff beschränken**, und wählen Sie dann eine Vorlage aus, um schnell die entsprechenden Nutzungsrechte anzuwenden, oder klicken Sie auf **Zugriff beschränken**, und wählen Sie die Nutzungsrechte selbst aus.

    > [!NOTE]
    > Wenn Sie Rights Management zum ersten Mal verwenden, stellen Sie eine Verbindung mit dem [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]-Dienst her. Hierbei werden Sie zur Eingabe von Anmeldeinformationen aufgefordert, um den Office-IRM-Client zu konfigurieren.

3.  Speichern Sie das Dokument.

Wenn das Dokument von anderen geöffnet wird, werden sie zuerst authentifiziert. Wenn Sie nicht autorisiert sind, um das Dokument zu öffnen, wird es nicht geöffnet. Wenn sie zum Öffnen des Dokuments autorisiert sind, wird es mit den eingeschränkten Nutzungsrechten, die für diesen Benutzer angegeben wurden, geöffnet. Beispielsweise gestattet ein Nutzungsrecht „Nur anzeigen“ dem Benutzer nicht das Bearbeiten oder Speichern des Dokuments, auch nicht, wenn es vorher an einen anderen Speicherort kopiert wird. Die Nutzungsrechte werden am oberen Rand des Dokuments in einem Einschränkungsbanner angezeigt. In dem Banner können die Berechtigungen angezeigt werden, die auf das Dokument angewendet werden, oder es kann ein Link zu deren Anzeige vorhanden sein.

#### So schützten Sie eine E-Mail mithilfe von Outlook 2013 und Exchange Online

1.  Erstellen Sie in Outlook eine neue E-Mail, die an einen Empfänger in Ihrer Organisation adressiert ist.

2.  Klicken Sie auf der Registerkarte **OPTIONEN** auf **Berechtigung**, und wählen Sie dann eine Option aus. Beispiel: **Nicht weiterleiten**, **&lt;Unternehmensname&gt; – Vertraulich** oder **&lt;Unternehmensname&gt; – Nur vertrauliche Ansicht**.

3.  Senden Sie die Nachricht.

Ähnlich wie beim Anzeigen eines geschützten Dokuments, werden die Empfänger der E-Mail bei deren Empfang zuerst authentifiziert. Wenn sie zum Anzeigen der E-Mail autorisiert sind, wird sie mit den eingeschränkten Nutzungsrechten, die für diesen Benutzer angegeben wurden, geöffnet. Wenn Sie beispielsweise **Nicht weiterleiten** ausgewählt haben, ist die Schaltfläche „Weiterleiten“ im Menüband nicht verfügbar.

#### So schützten Sie eine E-Mail mithilfe von Outlook Web App

1.  Erstellen Sie in Outlook Web App eine neue E-Mail, die an einen Empfänger in Ihrer Organisation adressiert ist.

2.  Klicken Sie auf **...**, auf **Berechtigung festlegen**, und wählen Sie dann eine Option aus. Beispiel: **Nicht weiterleiten**, **Nicht allen antworten**, **&lt;Unternehmensname&gt; – Vertraulich** oder **&lt;Unternehmensname&gt; – Nur vertrauliche Ansicht**.

3.  Senden Sie die Nachricht.

Ähnlich wie beim Anzeigen eines geschützten Dokuments, werden die Empfänger der E-Mail bei deren Empfang zuerst authentifiziert. Wenn sie zum Anzeigen der E-Mail autorisiert sind, wird sie mit den eingeschränkten Nutzungsrechten, die für diesen Benutzer angegeben wurden, geöffnet. Wenn Sie beispielsweise **Nicht allen antworten** ausgewählt haben, ist die Option **ALLEN ANTWORTEN** im Nachrichtenfenster nicht verfügbar.

## Siehe auch
[Verwenden von Azure Rights Management](../Topic/Using_Azure_Rights_Management.md)


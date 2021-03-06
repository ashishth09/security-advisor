---

copyright:
  years: 2014, 2018
lastupdated: "2018-11-15"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}

# {{site.data.keyword.security-advisor_short}} einrichten
{: #setup}

Mit {{site.data.keyword.security-advisor_long}} können Sie Ihre Apps kontinuierlich auf Sicherheitsrisiken und -bedrohungen überwachen. Wenn Sicherheitslücken gefunden werden, werden Sie über das Service-Dashboard benachrichtigt.{:shortdesc}

## Sicherheitslücken in Container-Images überwachen
{: #setup_images}

Ein Docker-Image ist die Basis jedes Containers, den Sie erstellen. Das Image könnte Ihre App, deren Konfiguration und alle erforderlichen Abhängigkeiten enthalten. Ein Image wird in der Regel in einer Registry gespeichert. Durch die Verwendung von {{site.data.keyword.registryshort_notm}} haben Sie Zugriff auf Vulnerability Advisor, womit Ihre Images kontinuierlich auf mögliche Sicherheitsprobleme überprüft werden. Werden Probleme gefunden, werden Sie benachrichtigt und Sie haben die Möglichkeit, einen umfassenden Bericht in Ihrem {{site.data.keyword.security-advisor_short}}-Dashboard anzuzeigen.
{:shortdesc}

Weitere Informationen hierzu finden Sie unter [{{site.data.keyword.registryshort_notm}}](/docs/services/Registry/index.html#index).


**Vorbereitende Schritte**

Bevor Sie die Registry verwenden können, müssen Sie die folgenden Befehlszeilenschnittstellen und Plug-ins installiert werden:
- [Die {{site.data.keyword.Bluemix_notm}}-CLI ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://clis.ng.bluemix.net/ui/home.html)
- Das Plug-in 'Container-Registry'

    ```
    ibmcloud plugin install container-registry -r Bluemix
    ```
    {: pre}

</br>
**Namensbereich erstellen**

1. Melden Sie sich über die Befehlszeilenschnittstelle (CLI) bei Ihrem Konto an.

   ```
   bx login --sso
   ```
   {: pre}

2. Melden Sie sich bei {{site.data.keyword.registryshort_notm}} an.

   ```
   bx cr login
   ```
   {: pre}

3. Erstellen Sie wahlweise einen Namensbereich. Sie können immer einen vorhandenen Namensbereich verwenden.

   ```
   bx cr namespace-add
   ```
   {: pre}

3. Kennzeichnen Sie ein Image mit einem Tag.

   ```
   docker tag <image>:<tag> registry.ng.bluemix.net/<namespace>/<image>:<tag>
   ```
   {: pre}

5. Übertragen Sie das Image mit einer Push-Operation.

   ```
   docker push registry.ng.bluemix.net/<namespace>/<image>:<tag>
   ```
   {: pre}


Nachdem Sie Images mit einer Push-Operation in Ihren {{site.data.keyword.registryshort_notm}}-Namensbereich übertragen haben, werden Informationen zu allen gefundenen Sicherheitslücken auf der Karte **Images mit Sicherheitslücken** im Service-Dashboard angezeigt. Sie können auch eine Drilloperation für bestimmte Images durchführen, um weitere Informationen zu erhalten, z. B. eine Beschreibung aller bekannten Sicherheitslücken und Konfigurationsprobleme, die identifiziert wurden.

</br>

## Zertifikate überwachen
{: #setup_certificates}

Wussten Sie, dass {{site.data.keyword.cloudcerts_long_notm}} die Überwachung und Verwaltung Ihrer SSL/TLS-Zertifikate unterstützen kann? Durch die Integration von {{site.data.keyword.cloudcerts_short}} und {{site.data.keyword.security-advisor_short}} können Sie Alerts und Erinnerungen empfangen, die Sie darüber informieren, wann Sie Ihre Zertifikate und andere Informationen aktualisieren sollten, wodurch sich spätere Sicherheitslücken verhindern lassen können.
{:shortdesc}

Weitere Informationen hierzu finden Sie unter [{{site.data.keyword.cloudcerts_long_notm}}](/docs/services/certificate-manager/index.html#gettingstarted).

1. Suchen Sie im {{site.data.keyword.Bluemix_notm}}-Katalog nach "{{site.data.keyword.cloudcerts_short}}".
2. Geben Sie der Serviceinstanz einen Namen oder verwenden Sie den vorgegebenen Namen.
3. Klicken Sie auf **Erstellen**.
4. Klicken Sie auf **Zertifikat importieren**, um die Zertifikate Ihrer Organisation in {{site.data.keyword.cloudcerts_short}} zu importieren.

Nachdem Sie Ihre Zertifikate importiert haben, werden auf der Karte **Zertifikate** im {{site.data.keyword.security-advisor_short}}-Dashboard Informationen wie Ablaufzeiten und abgelaufene Zertifikate angezeigt. Wenn Sie auf die Karte klicken, erhalten Sie ausführlichere Informationen zu den Zertifikaten, z. B. zu welcher Serviceinstanz die Zertifikate gehören. Darüber hinaus werden alle Maßnahmen angezeigt, mit denen Sie die Sicherheitslücken schließen können.

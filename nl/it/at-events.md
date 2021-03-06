---

copyright:
  years: 2017, 2018
lastupdated: "2018-10-11"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}


# Eventi di {{site.data.keyword.cloudaccesstrailshort}}
{: #at_events}

Puoi visualizzare, gestire e controllare le attività avviate dall'utente effettuate nella tua istanza del servizio {{site.data.keyword.security-advisor_long}} utilizzando il servizio {{site.data.keyword.cloudaccesstrailshort}}.
{: shortdesc}

Per ulteriori informazioni su come funziona il servizio, consulta la [documentazione {{site.data.keyword.cloudaccesstrailshort}}](/docs/services/cloud-activity-tracker/index.html).


## Dove visualizzare gli eventi
{: #monitor}

Gli eventi sono disponibili nel **dominio dell'account** {{site.data.keyword.cloudaccesstrailshort}} disponibile nella regione {{site.data.keyword.Bluemix_notm}} in cui vengono generati gli eventi.

1. Accedi al tuo account {{site.data.keyword.Bluemix_notm}}.
2. Dal catalogo, esegui il provisioning di un'istanza del servizio {{site.data.keyword.cloudaccesstrailshort}} nello stesso account della tua istanza di {{site.data.keyword.security-advisor_long}}.
3. Sulla scheda **Gestisci** del dashboard {{site.data.keyword.cloudaccesstrailshort}}, fai clic su **Visualizza in Kibana**. 
4. Imposta l'intervallo di tempo per il quale desideri visualizzare i log. Il valore predefinito è 15 minuti. 
5. Nell'elenco **Campi disponibili**, fai clic su **type**. Fai clic sull'icona della lente di ingrandimento del **Programma di traccia dell'attività** per limitare i log a quelli tracciati dal servizio. 
6. Puoi utilizzare gli altri campi disponibili per restringere la tua ricerca. 

Per utenti diversi dal proprietario dell'account, per visualizzare i log, devi utilizzare il piano premium. Per consentire ad altri utenti di visualizzare gli eventi, consulta [Concessione di autorizzazioni per visualizzare gli eventi di account](/docs/services/cloud-activity-tracker/how-to/grant_permissions.html#grant_permissions).
{: tip}

## Elenco degli eventi
{: #events}

Consulta la seguente tabella per un elenco di eventi inviati a {{site.data.keyword.cloudaccesstrailshort}}.
{: shortdesc}

<table>
  <tr>
    <th>Azione </th>
    <th>Descrizione </th>
  </tr>
  <tr>
    <td><code>security-advisor.metadata.read</code></td>
    <td>Visualizza una nota o le note create precedentemente.</td>
  </tr>
  <tr>
    <td><code>security-advisor.metadata.write</code></td>
    <td>Crea una nota.</td>
  </tr>
  <tr>
    <td><code>security-advisor.metadata.delete</code></td>
    <td>Elimina una nota.</td>
  </tr>
  <tr>
    <td><code>security-advisor.metadata.update</code></td>
    <td>Aggiorna una nota.</td>
  </tr>
  <tr>
    <td><code>security-advisor.findings.read</code></td>
    <td>Visualizza una o più ricorrenze.</td>
  </tr>
  <tr>
    <td><code>security-advisor.findings.write</code></td>
    <td>Crea una ricorrenza.</td>
  </tr>
  <tr>
    <td><code>security-advisor.findings.delete</code></td>
    <td>Elimina una ricorrenza.</td>
  </tr>
  <tr>
    <td><code>security-advisor.findings.update</code></td>
    <td>Aggiorna una ricorrenza.</td>
  </tr>
</table>

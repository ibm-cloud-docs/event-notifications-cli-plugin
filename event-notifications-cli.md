---

copyright:
  years: 2021, 2022
lastupdated: "2022-12-12"

keywords: event notifications CLI plug-in, CLI reference, en cli reference, event notifications cli reference, event notifications, command line reference

subcollection: event-notifications

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.en_short}} CLI
{: #event-notifications-cli}

The {{site.data.keyword.cloud_notm}} command-line interface (CLI) provides extra capabilities for service offerings. {{site.data.keyword.cloud_notm}} CLI supports a plug-in framework to extend its capability. You can install the {{site.data.keyword.en_short}} CLI plug-in from the {{site.data.keyword.cloud_notm}} plug-in repository. With the {{site.data.keyword.en_short}} service CLI plug-in, you can easily manage {{site.data.keyword.en_short}} service instances by using the CLI commands available.
{: shortdesc}

## Prerequisites
{: #en-cli-prereq}

- An {{site.data.keyword.cloud_notm}} account. If you do not have an account, click [here](https://cloud.ibm.com/) to create one.
- An instance of [{{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}}](https://cloud.ibm.com/catalog/services/event-notifications) service.
- [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-install-ibmcloud-cli) package on your local system.

When you log in to the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started){: external}, you're notified when updates are available. Be sure to keep your CLI up-to-date so that you can use the commands and flags that are available for the {{site.data.keyword.en_short}} CLI plug-in.
{: tip}

[IBM Cloud Quick Reference card](https://cloud.ibm.com/media/docs/downloads/IBM%20Cloud%20CLI%20quick%20reference.pdf).
{: note}

## Install the {{site.data.keyword.en_short}} CLI
{: #en-cli-install}

Install the {{site.data.keyword.en_short}} CLI plug-in by using the `plugin install` command.

```sh
ibmcloud plugin install en
```
{: pre}

## {{site.data.keyword.en_short}} CLI commands
{: #en-cli-commands}

### ibmcloud event-notifications init
{: #en-cli-init-command}

Set the instance that you'll we working on by using the following command:

```sh
ibmcloud event-notifications init [--instance-id INSTANCE-ID]
```
{: pre}

#### Command options
{: #en-cli-init-options}

`--instance-id` (string)
:  Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

   The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications environment variables set
{: #en-cli-environment-variables}

- export **IBMCLOUD_EN_ENDPOINT** variable to set the {{site.data.keyword.en_short}} region public endpoint.

   - **Dallas:** `https://us-south.event-notifications.cloud.ibm.com/event-notifications`
   - **London:** `https://eu-gb.event-notifications.cloud.ibm.com/event-notifications`
   - **Sydney:** `https://au-syd.event-notifications.cloud.ibm.com/event-notifications`
   - **Frankfurt:** `https://eu-de.event-notifications.cloud.ibm.com/event-notifications`

- export **IBMCLOUD_EN_ENDPOINT** variable to set the {{site.data.keyword.en_short}} region private endpoint.

   - **Dallas:** `https://private.us-south.event-notifications.cloud.ibm.com/event-notifications`
   - **London:** `https://private.eu-gb.event-notifications.cloud.ibm.com/event-notifications`
   - **Sydney:** `https://private.au-syd.event-notifications.cloud.ibm.com/event-notifications`
   - **Frankfurt:** `https://private.eu-de.event-notifications.cloud.ibm.com/event-notifications`

- export **EVENT_NOTIFICATIONS_API_KEY** variable to set the {{site.data.keyword.en_short}} instance `apikey`.

### ibmcloud event-notifications show
{: #en-cli-show-command}

Check your configuration.

```sh
ibmcloud event-notifications show
```
{: pre}

## Sources
{: #en-cli-source}

Operate on {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} source.

```sh
ibmcloud event-notifications source --help
```
{: pre}

### ibmcloud event-notifications source create
{: #en-cli-source-create-command}

- **Action:** Create `Source`.

   ```sh
   ibmcloud event-notifications source create --instance-id INSTANCE-ID --name NAME --description DESCRIPTION [--enabled ENABLED]
   ```
   {: pre}

- **Parameters to provide:**

   `--name NAME` (int64)
   :  The name to be provided for API source.

      The default value is ` `. The maximum length is `255` characters. The minimum length is `1` characters. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*()]*/`.

   `--description DESCRIPTION` (string)
   :  The description for source.

      The default value is ``. The maximum length is `255` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*()]*/`.

   `--enabled ENABLED` (Boolean)
   :  The Boolean flag to enable or disable the source.

      The value is set to true to enable the source and false to disable the source.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications source update
{: #en-cli-source-update-command}

- **Action:** Update `Source`.

   ```sh
   ibmcloud event-notifications source update --instance-id INSTANCE-ID --id ID [--name NAME] [--description DESCRIPTION] [--enabled ENABLED]
   ```
   {: pre}

- **Parameters to provide:**

   `--instance-id` (string)
   :  Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `--name` (int64)
   :  API Source name.

      The default value is ``. The maximum length is `255` characters. The minimum length is `1` characters. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*()]*/`.

   `--description` (int64)
   :  API Source Description

      The default value is ``. The maximum length is `255` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*()]*/`.

   `--enabled` (Boolean)
   :  Search string for filtering results.

      The value is set to true to enable the source and false to disable the source.

   `--id` (string)
   :  Unique identifier for Source. Required.

      The maximum length is `100` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z0-9-:_]*/`.

### ibmcloud event-notifications source list
{: #en-cli-source-list-command}

- **Action:** List all `Source`.

   ```sh
   ibmcloud event-notifications source list [--limit LIMIT] [--offset OFFSET] [--search SEARCH] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--limit LIMIT` (int64)
   :  The page limit for paginated results.

      The maximum value is `100`. The minimum value is `1`.

   `--offset OFFSET` (int64)
   :  The offset for paginated results.

      The minimum value is `0`.

   `--search SEARCH` (string)
   :  The search string for filtering results.

      The maximum length is `100` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z0-9]/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--force]`
   :  Activate to force resource deletion (to bypass the confirmation prompt).

### ibmcloud event-notifications source get
{: #en-cli-source-get-command}

- **Action:** Get specific `Source`.

   ```sh
   ibmcloud event-notifications source get --id ID [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  Unique identifier for source. Required.

      The maximum length is `100` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z0-9-:_]*/`.

   `--offset OFFSET`
   :  The offset for paginated results.

   `--search SEARCH`
   :  The search string for filtering results.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--force]`
   :  Activate to force resource deletion (to bypass the confirmation prompt).

### ibmcloud event-notifications source delete
{: #en-cli-source-delete-command}

- **Action:** Delete specific `Source`.

   ```sh
   ibmcloud event-notifications source delete --instance-id INSTANCE-ID --id ID
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  Unique identifier for source. Required.

      The maximum length is `100` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z0-9-:_]*/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--force]`
   :  Activate to force resource deletion (to bypass the confirmation prompt).

## Destinations
{: #en-cli-destination}

Operate on {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} destination.

```sh
ibmcloud event-notifications destination --help
```
{: pre}

### ibmcloud event-notifications destination create
{: #en-cli-destination-create}

- **Action:** Create a destination.

   ```sh
   ibmcloud event-notifications destination create --name NAME --type TYPE [--description DESCRIPTION] [--certificate CERTIFICATE] [--certificate-content-type CERTIFICATE-CONTENT-TYPE] [--config CONFIG] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--name NAME` (string)
   :  The name of the destination. Required.

      The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*() ]*/`.

   `--type TYPE` (string)
   :  The type of the destination. The options available are webhook, push_android, push_ios. Required.

      Allowable values are: `webhook`. The minimum length is `1` character.

   `--description DESCRIPTION` (string)
   :  The description of the destination.

      The default value is ` `. The maximum length is `255` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*() ]*/`.

   `--certificate CERTIFICATE` (string)
   :  The certificate file path to be provided. The allowed file type is p8 and p12 certificate. Provide file location to pass the certificate.

   `--certificate-content-type CERTIFICATE-CONTENT-TYPE` (string)
   :  The certificate content type to be set in the case of iOS destination. The default value is ``. The available options are: p8 or p12.

   `--config CONFIG` ([`DestinationConfig` examples](#en-cli-destination-config-example-schema))
   :  The configuration needed to set the destination-specific parameters.

   `--instance-id` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `--config`
   :  For webhook destinations only.

   ```json
   {
      "params" : {
         "url" : "exampleString",
         "verb" : "get",
         "custom_headers" : { },
         "sensitive_headers" : [ "exampleString" ]
      }
   }
   ```

- **Examples:**
{: #en-cli-destination-config-example-schema}

   - The following example shows format of the `DestinationConfig` object for iOS destination with P8 certificate. Set `pre_prod` Boolean parameter to *true* to configure destination as pre-production destination else set the value as *false*:

      ```json
      {
         "params" : {
            "cert_type" : "p8",
            "is_sandbox" : true,
            "key_id": "production",
            "team_id": "1234",
            "bundle_id": "test1",
            "pre_prod" : "true" // Set to true in case of configuring Destination as pre-prod Destination (pre_prod destination can only be configured for Standard plan)
         }
      }
      ```

   - The following example shows format of the `DestinationConfig` object for iOS destination with P12 certificate. Set `pre_prod` Boolean parameter to *true* to configure destination as pre-production destination else set the value as *false*.

      ```json
      {
         "params" : {
            "cert_type" : "p12",
            "is_sandbox" : true,
            "password": "apnspasswordvalue",
            "pre_prod" : "true" true // Set to true in case of configuring Destination as pre-prod Destination (pre_prod destination can only be configured for Standard plan)
         }
      }
      ```

   - The following example shows the format of the `DestinationConfig` object for Chrome destination. Set `pre_prod` Boolean parameter to *true* to configure destination as pre-production destination else set the value as *false*.

      ```json
      {
         "params" : {
            "api_key": "chromeapikey",
            "website_url" : "https://testwebsite.com",
            "pre_prod" : "true" true // Set to true in case of configuring Destination as pre-prod Destination (pre_prod destination can only be configured for Standard plan)
         }
      }
      ```

   - The following example shows format of the `DestinationConfig` object for Firefox destination. Set `pre_prod` Boolean parameter to *true* to configure destination as pre-production destination else set the value as *false*.

      ```json
      {
         "params" : {
            "website_url" : "https://testwebsite.com",
            "pre_prod" : "true" // Set to true in case of configuring Destination as pre-prod Destination (pre_prod destination can only be configured for Standard plan)
         }
      }
      ```

   - The following example shows format of the `DestinationConfig` object for Slack destination.

      ```json
      {
         "params" : {
            "url" : "https://hooks.slack.com/services/G0gyhsush/TYodsjhs/GHTbfidsimkk"
         }
      }
      ```

   - The following example shows format of the `DestinationConfig` object for Safari destination. Set `pre_prod` Boolean parameter to *true* to configure destination as pre-production destination else set the value as *false*.

      ```json
      {
         "params": {
            "cert_type":"p12",
            "certificate_name":"Users/Testuser/Documents/safari.p12",
            "password":"safarinew",
            "url_format_string":"https://test.com",
            "website_name":"testwebsite",
            "website_push_id":"test",
            "website_url":"https://test.com",
            "pre_prod" : "true" // Set to true in case of configuring Destination as pre-prod Destination (pre_prod destination can only be configured for Standard plan)
         }
      }
      ```

   - The following example shows format of the `DestinationConfig` object for MS Teams destination.

      ```json
      {
         "params" : {
            "url" : "https://xyz.webhook.office.com"
         }
      }
      ```

   - The following example shows format of the `DestinationConfig` object for {{site.data.keyword.openwhisk}} destination.

      ```json
      {
         "params" : {
            "url" : "https://www.ibmcfendpoint.com",
            "api_key" : "cffunctionnamespaceserviceidapikey"
         }
      }
      ```

   - The following example shows format of the `DestinationConfig` object for PagerDuty destination.

      ```json
      {
         "params" : {
            "routing_key" : "routingkeytoconnecttoPD",
            "api_key" : "cffunctionnamespaceserviceidapikey"
         }
      }
      ```

   - The following example shows the format of the `DestinationConfig` object for webhook.

      ```json
      {
         "params" : {
         "url" : "exampleString",
         "verb" : "get",
         "custom_headers" : { },
         "sensitive_headers" : [ "exampleString" ]
         }
      }
      ```

   - The following example shows the format of the `DestinationConfig` object for push_android destination.

      ```json
      {
         "params" : {
         "sender_id" : "sender_ID",
         "server_key" : "Server_key",
         "pre_prod" : true // Set to true in case of configuring Destination as pre-prod Destination (pre_prod destination can only be configured for Standard plan)
         }
      }
      ```

### ibmcloud event-notifications destination list
{: #en-cli-destination-list-command}

- **Action:** List all `Destination`.

   ```sh
   ibmcloud event-notifications destination list [--limit LIMIT] [--offset OFFSET] [--search SEARCH] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--limit LIMIT` (int64)
   :  The page limit for paginated results.

      The maximum value is `100`. The minimum value is `1`.

   `--offset OFFSET` (int64)
   :  The offset for paginated results.

      The minimum value is `0`.

   `--search SEARCH` (string)
   :  The search string for filtering results.

      The maximum length is `100` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z0-9]/`.

   `--instance-id` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications destination get
{: #en-cli-destination-get-command}

- **Action:** Get specific `Destination`.

   ```sh
   ibmcloud event-notifications destination get --id ID [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  The unique identifier for destination. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications destination update
{: #en-cli-destination-update-command}

- **Action:** Update existing `Destination`.

   ```sh
   ibmcloud event-notifications destination update --id ID [--name NAME] [--description DESCRIPTION] [--certificate CERTIFICATE] [--config CONFIG] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--id` (string)
   :  Unique identifier for destination. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `--name NAME` (string)
   :  The destination name to be updated.

      The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*() ]*/`.

   `--description DESCRIPTION` (string)
   :  The description of the destination.

      The default value is ` `. The maximum length is `255` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*() ]*/`.

   `--certificate CERTIFICATE` (string)
   :  The certificate file path to be provided. The allowed file type is p8 and p12 certificate.

   `--config CONFIG` ([`DestinationConfig` examples](#en-cli-destination-config-example-schema))
   :  The configuration needed to set the destination-specific parameters.

   `--instance-id`
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications destination delete
{: #en-cli-destination-delete-command}

- **Action:** Delete existing `Destination`.

   ```sh
   ibmcloud event-notifications destination delete --id ID [--instance-id INSTANCE-ID] [--force]
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  The unique identifier for destination. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.


   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--force]` (Boolean)
   :  Activate to force resource deletion (to bypass the confirmation prompt).

## Topics
{: #en-cli-topic}

Operate on {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} topic.

```sh
ibmcloud event-notifications topic --help
```
{: pre}

### ibmcloud event-notifications topic create
{: #en-cli-topic-create-command}

- **Action:** Create new `Topic`.

   ```sh
   ibmcloud event-notifications topic create --name NAME [--description DESCRIPTION] [--sources SOURCES] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--name NAME` (string)
   :  Name of the topic. Required.

      The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*()]*/`.

   `--description DESCRIPTION` (string)
   :  Description of the topic.

      The default value is ``. The maximum length is `255` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*()]*/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--sources SOURCES]` ([TopicCreateSourcesItem[]](#en-cli-topic-example-schema))
   :  The list of sources.

- **Example:**
{: #en-cli-topic-example-schema}

   - The following example shows the format of the `TopicCreateSourcesItem[]` object.

      ```json
      [
         {
            "id" : "exampleString",
            "rules" : [
               {
                  "enabled" : true,
                  "event_type_filter" : "$.*",
                  "notification_filter" : "exampleString"
               }
            ]
         }
      ]
      ```

   - The following example shows the format of the `TopicUpdateSourcesItem[]` object.

      ```json
      [
         {
            "id" : "exampleString",
            "rules" : [
               {
                  "enabled" : true,
                  "event_type_filter" : "exampleString",
                  "notification_filter" : "exampleString",
                  "rule_id" : "exampleString"
               }
            ]
         }
      ]
      ```

### ibmcloud event-notifications topic list
{: #en-cli-topic-list-command}

- **Action:** List all `Topic`.

   ```sh
   ibmcloud event-notifications topic list [--limit LIMIT] [--offset OFFSET] [--search SEARCH] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--limit LIMIT` (int64)
   :  The page limit for paginated results.

      The maximum value is `100`. The minimum value is `1`.

   `--offset OFFSET` (int64)
   :  The offset for paginated results.

      The minimum value is `0`.

   `--search SEARCH` (string)
   :  The search string for filtering results.

      The maximum length is `100` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z0-9]/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications topic get
{: #en-cli-topic-get-command}

- **Action:** Get specific `Topic`.

   ```sh
   ibmcloud event-notifications topic get --id ID [--include INCLUDE] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  Unique identifier for topic. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}/`.

   `--include INCLUDE` (string)
   :  Include sub topics.

      The default value is ``. The maximum length is `20` characters. The minimum length is `0` characters. The value must match regular expression `/[a-z]/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications topic update
{: #en-cli-topic-update-command}

- **Action:** Update existing `Topic`.

   ```sh
   ibmcloud event-notifications topic update --id ID [--name NAME] [--description DESCRIPTION] [--sources SOURCES] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--instance-id` (string)
   :  Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `--id` (string)
   :  Unique identifier for topic. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}/`.

   `--name` (string)
   :  Name of the topic.

      The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*()]*/`.

   `--description` (string)
   :  Description of the topic.

      The default value is ``. The maximum length is `255` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*()]*/`.

   `--sources` ([TopicUpdateSourcesItem[]](#en-cli-topic-example-schema))
   :  List of sources.

### ibmcloud event-notifications topic delete
{: #en-cli-topic-delete-command}

- **Action:** Delete existing `Topic`.

   ```sh
   ibmcloud event-notifications topic delete --id ID [--instance-id INSTANCE-ID] [--force]
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  Unique identifier for topic. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--force]` (Boolean)
   :  Activate to force resource deletion (to bypass the confirmation prompt).

## Subscriptions
{: #en-cli-subscription}

Operate on {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} subscription.

```sh
ibmcloud event-notifications subscription --help
```
{: pre}

### ibmcloud event-notifications subscription create
{: #en-cli-subscription-create-command}

- **Action:** Create new `Subscription`.

   ```sh
   ibmcloud event-notifications subscription create [--name NAME] [--description DESCRIPTION] [--destination-id DESTINATION-ID] [--topic-id TOPIC-ID] [--attributes ATTRIBUTES] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--name NAME` (string)
   :  The name to be set for subscription.

      The maximum length is `50` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*() ]*/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--description DESCRIPTION]` (string)
   :  The description to be set for subscription.

      The default value is ``. The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/.?:'";,+=!#@$%^&*() ]*/`.

   `[--destination-id DESTINATION-ID]` (string)
   :  The destination ID to be set for subscription.

      The maximum length is `150` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}/`.

   `[--topic-id TOPIC-ID]` (string)
   :  The topic ID to be set for subscription.

      The maximum length is `150` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}/`.

   `[-attributes ATTRIBUTES]` ([SubscriptionCreateAttributes](#en-cli-subscription-example-schema))
   :  The attributes to be set for subscription.

- **Examples:**
{: #en-cli-subscription-example-schema}

   - The following example shows the format of the `SubscriptionCreateAttributes` object.

      ```json
      {
         "add_notification_payload" : true,
         "signing_enabled" : true
      }
      ```

   - Attributes flag syntax in case of SMS subscription to be created.

      ```json
      {
         "to" :["+19667895490", "+19845678321"]
      }
      ```

   - Attributes flag syntax in case of email subscription to be created.

      ```json
      {
         "to" :["entest@gmail.com"],
         "add_notification_payload": true,
         "reply_to_mail": "en@ibm.com",
         "reply_to_name": "EYS ORG",
         "from_name":"ABC ORG"
      }
      ```

   - The following example shows the format of the `SubscriptionCreateAttributes` object for slack.

      ```json
      {
         "attachment_color" : "#FF0000"
      }
      ```

   - The following example shows the format of the `SubscriptionUpdateAttributes` object.

      ```json
      {
         "to" : [ "exampleString" ],
         "recipient_selection" : "only_destination"
      }
      ```

### ibmcloud event-notifications subscription list
{: #en-cli-subscription-list-command}

- **Action:** List all `Subscription`.

   ```sh
   ibmcloud event-notifications subscription list [--offset OFFSET] [--limit LIMIT] [--search SEARCH] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--limit LIMIT` (int64)
   :  The page limit for paginated results.

      The maximum value is `100`. The minimum value is `1`.

   `--offset OFFSET` (int64)
   :  The offset for paginated results.

      The minimum value is `0`.

   `--search SEARCH` (string)
   :  The search string for filtering results.

      The maximum length is `100` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z0-9]/`.

   `[--instance-id INSTANCE-ID]`  (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications subscription get
{: #en-cli-subscription-get-command}

- **Action:** Get specific `Subscription`.

   ```sh
   ibmcloud event-notifications subscription get --id ID [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  Unique identifier for subscription. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

### ibmcloud event-notifications subscription delete
{: #en-cli-subscription-delete-command}

- **Action:** Delete existing `Subscription`.

   ```sh
   ibmcloud event-notifications subscription delete --id ID [--instance-id INSTANCE-ID] [--force]
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  Unique identifier for subscription. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--force]` (Boolean)
   :  Activate to force resource deletion (to bypass the confirmation prompt).

### ibmcloud event-notifications subscription update
{: #en-cli-subscription-update-command}

- **Action:** Update existing `Subscription`.

   ```sh
   ibmcloud event-notifications subscription update --id ID [--name NAME] [--description DESCRIPTION] [--attributes ATTRIBUTES] [--instance-id INSTANCE-ID]
   ```
   {: pre}

- **Parameters to provide:**

   `--id ID` (string)
   :  Unique identifier for subscription. Required.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}/`.

   `[--name NAME]` (string)
   :  The updated description to be set for subscription.

      The maximum length is `100` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z0-9-:_]*/`.

   `[--instance-id INSTANCE-ID]` (string)
   :  The Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `[--description DESCRIPTION]` (string)
   :  The updated description to be set for subscription.

      The default value is ``. The maximum length is `100` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z0-9-:_]*/`.

   `[-attributes ATTRIBUTES]` ([SubscriptionUpdateAttributes](#en-cli-subscription-example-schema))
   :  The attributes to be set for subscription

## Integrations
{: #en-cli-integration}

Operate on {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} integration.

```sh
ibmcloud event-notifications Integration --help
```

### ibmcloud event-notifications integration replace
{: #en-cli-integration-update-command}

Replace `Integration`.

```sh
ibmcloud event-notifications Integration replace --instance-id INSTANCE-ID --id ID --type Type --metadata METADATA
```

#### Command options
{: #en-cli-integration-replace-options}

`--instance-id` (string)
:  Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

   The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

`--type` (string)
:  Type of the integration KMS/hs-crypto.

   The maximum length is `50` characters. The minimum length is `1` characters. Allowed values are KMS and hs-crypto.

`--metadata` ([IntegrationReplaceAttributes](#en-cli-integration-example-schema))
:  Integration schema for update

   Metadata required for integration.

`--id` (string)
:  Unique identifier for integration. Required.

   The maximum length is `100` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z0-9-:_]*/`.

- **Examples:**
{: #en-cli-integration-example-schema}

   - The following example shows the format of the `IntegrationReplaceAttributes` object.

      ```json
      {
         "endpoint" : "https://qa.us-south.kms.test.cloud.ibm.com",
         "crn" : "crn of key protect/hpcs instance",
         "root_key_id" : "root key id"
      }
      ```

### ibmcloud event-notifications integration list
{: #en-cli-integration-list-command}

List all `Integrations`.

```sh
ibmcloud event-notifications Integration list [--limit LIMIT] [--offset OFFSET] [--search SEARCH] [--instance-id INSTANCE-ID]
```

#### Command options
{: #event-notifications-Integration-list-cli-options}

`--instance-id` (string)
:  Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

   The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

`--limit` (int64)
:  Page limit for paginated results.

   The maximum value is `100`. The minimum value is `1`.

`--offset` (int64)
:  offset for paginated results.

   The minimum value is `0`.

`--search` (string)
:  Search string for filtering results.

   The maximum length is `100` characters. The minimum length is `0` characters. The value must match regular expression `/[a-zA-Z0-9]/`.

### ibmcloud event-notifications Integration get
{: #en-cli-integration-get-command}

Get specific `Integration`.

```sh
ibmcloud event-notifications Integration get --id ID [--instance-id INSTANCE-ID]
```

#### Command options
{: #en-cli-integration-get-options}

`--instance-id` (string)
:  Unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

   The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

`--id` (string)
:  Unique identifier for integration. Required.

   The maximum length is `100` characters. The minimum length is `1` character. The value must match regular expression `/[a-zA-Z0-9-:_]*/`.

## Send notifications
{: #en-cli-send-notifications}

### ibmcloud event-notifications Send notifications
{: #en-cli-send-notifications-command}

- **Action:** Use below command to send notifications in **cli version 0.0.7**.

   ```sh
   ibmcloud event-notifications send-notifications --instance-id INSTANCE-ID --subject SUBJECT --severity SEVERITY --id ID --source SOURCE --en-source-id EN-SOURCE-ID --type TYPE --time TIME [--data DATA] [--push-to PUSH-TO] [--message-fcm-body MESSAGE-FCM-BODY] [--message-apns-headers MESSAGE-APNS-HEADERS] [--message-apns-body MESSAGE-APNS-BODY] [--datacontenttype DATACONTENTTYPE] [--specversion SPECVERSION]
   ```
   {: pre}

- **Action:** Use below command to send notifications in **cli version 0.0.8** and higher.

   ```sh
   ibmcloud event-notifications send-notifications --instance-id INSTANCE-ID [--body BODY] [--ce-ibmenseverity CE-IBMENSEVERITY] [--ce-ibmendefaultshort CE-IBMENDEFAULTSHORT] [--ce-ibmendefaultlong CE-IBMENDEFAULTLONG] [--ce-ibmenfcmbody CE-IBMENFCMBODY] [--ce-ibmenapnsbody CE-IBMENAPNSBODY] [--ce-ibmenpushto CE-IBMENPUSHTO] [--ce-ibmenapnsheaders CE-IBMENAPNSHEADERS] [--ce-ibmenchromebody CE-IBMENCHROMEBODY] [--ce-ibmensafaribody CE-IBMENSAFARIBODY] [--ce-ibmenfirefoxbody CE-IBMENFIREFOXBODY] [--ce-ibmenchromeheaders CE-IBMENCHROMEHEADERS] [--ce-ibmenfirefoxheaders CE-IBMENFIREFOXHEADERS] [--ce-ibmensourceid CE-IBMENSOURCEID] [--ce-id CE-ID] [--ce-source CE-SOURCE] [--ce-type CE-TYPE] [--ce-specversion CE-SPECVERSION] [--ce-time CE-TIME]
   ```
   {: pre}

- **Action:** Use below command to send notifications in **cli version 0.1.1** and higher.

   ```sh
    ibmcloud event-notifications send-notifications --instance-id INSTANCE-ID [--body BODY]
   ```

- **Parameters to provide:**

   `[--instance-id INSTANCE-ID]` (string)
   :  The unique identifier for {{site.data.keyword.cloud_notm}} {{site.data.keyword.en_short}} instance.

      The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]/`.

   `--subject SUBJECT` (string)
   :  The subject for notification.

      The minimum length is `1` character.

   `[--severity SEVERITY]` or `--ce-ibmenseverity CE-IBMENSEVERITY` (string)
   :  The level of severity for notification. Required.

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/`.

   `--id` or `--ce-id` (string)
   :  The Notification ID. Required

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/`.

   `[--source SOURCE]` or `-ce-source CE-SOURCE` (string)
   :  The source description. Required

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/`.

   `[--en-source-id]` or `--ce-ibmensourceid CE-IBMENSOURCEID` (string)
   :  The source ID to be set for Notification source. Required.

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/`.

   `[--type TYPE]` or `[--ce-type CE-TYPE]` (string)
   :  The type of notification. Required.

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/`.

   `[--time TIME]` or `[--time TIME]` (string)
   :  The Timestamp to be set for notification. Required.

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/`.

   `[--datacontenttype DATACONTENTTYPE]` (string)
   :  The data content type for notification. Required.

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_\/`. Default value is application/json.

   `[--specversion SPECVERSION]` or `[--ce-specversion CE-SPECVERSION]` (string)
   :  The spec version value. Default value to be used is 1.0.

      The minimum length is `1` character. The value must match regular expression `/[0-9]`. Default value is 1.0.

   `[--push-to PUSH-TO]` or `[--ce-ibmenpushto CE-IBMENPUSHTO]` [DeviceDataConfiguration](#en-cli-send-notification-example-schema)
   :  The Device data information to send data in case of Registered Devices / Users IDs / Platforms. For broadcast, choose {}.

   `[--message-fcm-body MESSAGE-FCM-BODY]` or `[--ce-ibmenfcmbody CE-IBMENFCMBODY]` [FCMMessageBodyDataPayload](#en-cli-send-notification-example-schema)
   :  FCM message body to send notification to FCM devices.

   `[--message-apns-headers MESSAGE-APNS-HEADERS]` or `[--ce-ibmenapnsheaders CE-IBMENAPNSHEADERS]` [APNSHeaders#en-cli-send-notification-example-schema)
   :  The Custom APNS headers information can be set by using this option.

   `[--message-apns-body MESSAGE-APNS-BODY]` or `[--ce-ibmenapnsbody CE-IBMENAPNSBODY]` [APNSMessageBody](#en-cli-send-notification-example-schema)
   :  The apns message body can be set by using this option.

   `[--body BODY]` [DataPayload](#en-cli-send-notification-example-schema))
   :  The body payload to be provided for notification.

   `[--ce-ibmendefaultshort]` (string)
   :  The short text for notification to send.

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_/.?:'\";,+=!#@$%^&*() ]*/`.

   `[--ce-ibmendefaultlong CE-IBMENDEFAULTLONG]` (string)
   :  The long text for notification top sends.

      The minimum length is `1` character. The value must match regular expression `/[a-zA-Z 0-9-_/.?:'\";,+=!#@$%^&*() ]*/`.

   `[--ce-ibmenchromebody CE-IBMENCHROMEBODY]` [ChromeMessageBody](#en-cli-send-notification-example-schema)
   :  Chrome message body to send notification to FCM devices.

   `[--ce-ibmensafaribody CE-IBMENSAFARIBODY]`
   :  Safari message body to send notification to Safari devices.

   `[--ce-ibmenfirefoxbody CE-IBMENFIREFOXBODY]` [FirefoxMessageBody](#en-cli-send-notification-example-schema)
   :  Firefox message body to send notification to FCM devices.

   `[--ce-ibmenchromeheaders CE-IBMENCHROMEHEADERS]` [ChromeHeaders](#en-cli-send-notification-example-schema)
   :  The Custom Chrome headers information can be set by using this option.

   `[--ce-ibmenfirefoxheaders CE-IBMENFIREFOXHEADERS]` [FirefoxHeaders](#en-cli-send-notification-example-schema)
   :  The Custom Firefox information can be set by using this option.

- **Examples:**
{: #en-cli-send-notification-example-schema}

   - The following example shows the format of data payload for sending notifications.

      ```json
      {
         "data": {
            "createTimestamp": 1557282940339,
            "severity": "LOW",
            "shortDescription": "examplestring"
         }
      }
      ```

   - The following example shows the format of FCM message body to send notification to FCM devices.

      ```json
      {"message":{
         "data":{
              "alert": "examlestring", "delay_while_idle":true,"time_to_live":2,"collapse_key":"testCollapseKey","notification":{"title":"Match update","body":"Arsenal goal in added time, score is now 3-0"},"data":{"alert":"Notification alert message","url":"https","payload":{"mydevicearra":["cc75e4a6-edd8-3bec-a7c3-dfca6572a03b"]}}
              }
         }
      }
      ```

   - The following example shows the format of Chrome message body to send notification to FCM devices.

      ```json
      {"title":"Hello Chrome", "en_data":{"alert":"Hello Chrome Notification","title":"Chrome New Title","iconUrl":"https://","timeToLive":100,"payload":{"key":"value"}}}
      ```

   - The following example shows the format of Firefox message body to send notification to FCM devices.

      ```json
      '{"title":"Hello Firefox", "en_data":{"alert":"Hello firefox Notification","title":"firefox New Title","iconUrl":"https://","timeToLive":100,"payload":{"key":"value"}}}'
      ```

   - The following example shows the format of apns/chrome/fireox custom headers.

      ```json
      {
          "test": "test header",
          "new": "newmessage"
      }
      ```

   - The following example shows the format of APNS message body to send notification to FCM devices.

      ```json
      {"data":{"alert":"alert","url":"https","badge":9,"sound":"bingbong.aiff","payload":"{\\\"fcm_devices\\\": [\\\"cc75e4a6-edd8-3bec-a7c3-dfca6572a03b\\\"]}","type":"DEFAULT","subtitle":"dummy","title":"dummy1","body":"body","ios_action_key":"key","interactive_category":"interactiveCategory","title_loc_key":"titleLocKey","loc_key":"GAME_PLAY_REQUEST_FORMAT","launch_image":"image.png","title_loc_args":["Shelly","Rick"],"loc_args":["Shelly","Rick"],"attachment_url":"some url","apns_collapse_id":"12","apns_thread_id":"1","apns_group_summary_arg":"apnsGroupSummaryArg","apns_group_summary_arg_count":1}}
      ```

   - The following example shows the format of body to send notification to slack destination.

      ```json
      {"specversion" : "1.0","source": "github.io/pr","ibmensourceid": "4e22c0fe-5db3-49ce-9b86-47d3fd57f7a8:api","id":"1234-1234-sdfs-234", "time" : "2018-04-05T17:31:00Z","type":"com.ibm.cloud.compliance.certificate_manager:certificate_expired", "subject":"12345678",  "ibmenseverity":"HIGH","ibmensmstext":"Test message for EN - 5syat56","ibmensubject":"Findings on IBM Cloud Security Advisor's","ibmenhtmlbody":" \"Hi  ,<br/>Certificate expiring in 90 days.<br/><br/>Please login to <a href=\"https: //cloud.ibm.com/security-compliance/dashboard\">Security and Complaince dashboard</a> to find more information<br/>\" ","ibmendefaultshort":"Security findings in your IBM Cloud Account","ibmendefaultlong":"Certificate expiring in 90 days. Please login to cloud console to find more information","ibmenfcmbody": "{\"notification\":{\"title\":\"Hello, Tag!\",\"time_to_live\":100}}",
      "ibmenapnsbody": "{\"en_data\":{\"alert\":\"alert\"},\"aps\":{\"alert\":{\"loc-args\":[\"Shelly\",\"Rick\"],\"action-loc-key\":\"key\",\"launch-image\":\"image.png\",\"loc-key\":\"GAME_PLAY_REQUEST_FORMAT\",\"subtitle\":\"Tes Sub apns 9\",\"summary-arg\":\"apnsGroupSummaryArg\",\"body\":\"Pradeep Notification 10\",\"title-loc-key\":\"titleLocKey\",\"title\":\"Test apns 9\",\"summary-arg-count\":1,\"title-loc-args\":null},\"badge\":9,\"sound\":\"bingbong.aiff\",\"category\":\"interactiveCategory\",\"thread-id\":\"12\",\"mutable-content\":1},\"url\":\"https\",\"apns-collapse-id\":\"10\",\"attachment-url\":\"some url\"}",
      "message_apns_headers": "{\"apns-collapse-id\": \"13\"}", "ibmenapnsheaders": "{\"apns-collapse-id\": \"13\"}","ibmenchromebody": "{\"title\":\"Hello Chrome\", \"en_data\":{\"alert\":\"Hello Chrome Notification\",\"title\":\"Chrome New Title\",\"iconUrl\":\"https://\",\"timeToLive\":100,\"payload\":{\"key\":\"value\"}}}","ibmenfirefoxbody": "{\"title\":\"Hello Firefox\", \"en_data\":{\"alert\":\"Hello Firefox Notification\",\"title\":\"Firefox New Title\",\"iconUrl\":\"https://\",\"timeToLive\":100,\"payload\":{\"key\":\"value\"}}}","ibmenfirefoxheaders": "{\"TTL\":100}","ibmenchromeheaders":"{\"TTL\":100}" ,"ibmenpushto": "{\"platforms\":[\"push_ios\"]}","datacontenttype" : "application/json", "data": {"author": {"account_id": "dgduyeiueiinchdidkuedfrr","email": "testuser@gmail.com","id": "IBMid-76893","kind": "user" },"create_time": "2022-02-28T13:28:14.043755123Z","create_timestamp": 1646054894,"issuer": "IBM Cloud Security and Compliance Center","issuer_url": "https://cloud.ibm.com/security-compliance","long_description": "Success! Your Event Notifications instance is configured with IBM Cloud Security and Compliance Center.","payload_type": "test","reported_by": {"id": "compliance","title": "IBM Cloud Security and Compliance Center", "url": "https://cloud.ibm.com/security-compliance"},"severity": "LOW","short_description": "Success! Your Event Notifications instance is configured with IBM Cloud Security and Compliance Center.","transaction_id":"6a25fd3d-8530-43b9-96a5-ede2a7712bc9"}
      ```

   - The following example shows the target device configuration example.

      ```json
      {"fcm_devices": ["deviceidstring"],"user_ids": ["useridstring"], "platforms": ["G"]}
      ```

   - The following example shows the send notification general payload for cli version above 0.1.1

      ```json
      ibmcloud en send-notifications --instance-id <instance-id> --body '{"id": "b2198eb8-04b1-48ec-a78c-ee87694dd845", "time": "2018-04-05T17:31:00Z","type": "*","subject": "This is a simple monitoring test alert!!","message_text": "Hi, Welcome from the IBM Cloud - Event Notifications service!", "message_subject": "This is a simple monitoring test alert!!","source": "apisource/git", "specversion": "1.0","ibmensourceid": "e9785d21-4780-467a-8836-c530f5v6738:api","data": {"alert": "En Proactive monitoring","message": "Hi, Welcome from the IBM Cloud - Event Notifications service"},"ibmenfcmbody": "{\"notification\": {\"title\": \"En Proactive monitoring test alert!\"}}","ibmenpushto": "{\"platforms\": [\"push_chrome\", \"push_firefox\", \"push_android\"]}","ibmenapnsbody": "{\"aps\": {\"alert\": \"En Proactive monitoring test alert!\"}}","ibmenchromebody": "{\"title\": \"En Proactive monitoring test alert!\"}","ibmenchromeheaders": "{\"TTL\": 3600}","ibmenfirefoxbody": "{\"title\": \"En Proactive monitoring test alert!\"}","ibmenfirefoxheaders": "{\"TTL\": 3600}","datacontenttype": "application/json","ibmendefaultlong": "Hi, we are making sure from our side that the service is available for consumption. If you are receiving this event, it means we doing fine. Thank you.","ibmendefaultshort": "This is a proactive monitoring test alert from IBM Cloud Event Notifications service."}'
      ```

#### Additional properties that can be configured for the iOS notification
{: #en-cli-send-notifications-command-addprops-ios}

|  Property  |  Property type  |  Description  |
|-------------|-------------|-------------|
| `badge` | integer | The number to display as the badge of the application icon. |
| `interactive_category` | string | The category identifier to be used for the interactive push notifications. |
| `ios_action_key` | string |The title for the Action key. |
| `payload` | JSON object | Custom JSON payload that is sent as part of the notification message. |
| `sound` | string | The name of the sound file in the application bundle. The sound of this file is played as an alert. |
| `title_loc_key` | string | The key to a title string in the Localizable.strings file for the current localization. The key string can be formatted with %@ and %n$@ specifiers to take the variables specified in the titleLocArgs array. |
| `loc_key` | string | A key to an alert-message string in a Localizabl.strings file for the current localization (which is set by the user's language preference). The key string can be formatted with %@ and %n$@ specifiers to take the variables specified in the locArgs array. |
| `launch_image` | string | The file name of an image file in the app bundle, with or without the file name extension. The image is used as the launch image when users tap the action button or move the action slider. |
| `title_loc_args` | string | Variable string values to appear in place of the format specifiers in title-loc-key. |
| `loc_args` | string | Variable string values to appear in place of the format specifiers in locKey. | title string The title of Rich Push notifications (Supported only on iOS 10 and above).|
| `title` | string | The title of Rich Push notifications (Supported only on iOS 10 and above). |
| `subtitle` | string | The subtitle of the Rich notifications (Supported only on iOS 10 and above). |
| `body` | string | The body for IOS notifications. |
| `attachment_url` | string | The link to the iOS notifications media (video, audio, GIF, images - Supported only on iOS 10 and above). |
| `type` | string | Allowable values: DEFAULT, MIXED, SILENT. |
| `apns_collapse_id` | string | Multiple notifications with the same collapse identifier are displayed to the user as a single notification. |
| `apns_thread_id` | string | An app-specific identifier for grouping related notifications. This value corresponds to the threadIdentifier property in the UNNotificationContent object. |
| `apns_group_summary_arg` | string | The string the notification adds to the category’s summary format string. |
| `apns_group_summary_arg_count` | integer | The number of items the notification adds to the category’s summary format string. |
{: caption="Table 1. iOS platform settings" caption-side="bottom"}

#### Additional properties that can be configured for the FCM notification
{: #en-cli-send-notifications-command-addprops-fcm}

|  Property  |  Property type  |  Description  |
|-------------|-------------|-------------|
| `icon` | string | Specify the name of the icon to be displayed for the notification. Make sure that the icon is already packaged with the client application. |
| `delay_while_idle` | Boolean | When set to true, this parameter indicates that the message should not be sent until the device becomes active. |
| `sync` | Boolean | Device group messaging makes it possible for every app instance in a group to reflect the latest messaging state. |
| `visibility` | string | private or public - Visibility of this notification, which affects how and when the notifications are revealed on a secure locked screen. |
| `redact` | string | Content that is specified shows up on a secure locked screen on the device when visibility is set to Private. |
| `payload` | JSON object | Custom JSON payload that is sent as part of the notification message.|
| `priority` | string | A string value that indicates the priority of this notification. Allowed values are 'max', 'high', 'default', 'low' and 'min'. High/Max priority notifications along with 'sound' field might be used for Heads up notification in Android 5.0 or higher.sampleval='low'. |
| `sound` | string| The sound file (on device) that will be attempted to play when the notification arrives on the device. |
| `time_to_live` | integer | Specifies how long (in seconds) the message should be kept in GCM storage if the device is offline.
| `lights` |  | Sets the notification LED color on receiving push notification. |
| `ledArgb` | string | The color of the LED. The hardware does its best approximation. |
| `ledOnMs` | integer | The time in milliseconds for the LED to be on while it's flashing. The hardware does its best approximation. |
| `ledOffMs` | string | The time in milliseconds for the LED to be off while it's flashing. The hardware does its best approximation. |
| `android_title` | string | The title of Rich Push notifications. |
| `group_id` | string | Set this notification to be part of a group of notifications sharing the same key. Grouped notifications might display in a cluster or stack on devices that support such rendering. |
| `style` |  | Options to specify for Android expandable notifications. The types of expandable notifications are picture_notification, bigtext_notification, inbox_notification. |
| `type` | string | Specifies the type of expandable notifications. The possible values are bigtext_notification, picture_notification, inbox_notification.|
| `title` | string | Specifies the title of the notification. The title is displayed when the notification is expanded. Title must be specified for all three expandable notifications. |
| `type` | string | Allowed values: DEFAULT, SILENT. |
| `alert` | string | The alert value of Notification. |
{: caption="Table 2. Android platform settings" caption-side="bottom"}

:orphan:
:nosearch:

Configure the network environment in which Mattermost is deployed by going to **System Console > Environment > Web Server**, or by updating the ``config.json`` file as described in the following tables. Changes to configuration settings in this section require a server restart before taking effect.

.. config:setting:: web-siteurl
  :displayname: Site URL (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.SiteURL
  :environment: MM_SERVICESETTINGS_SITEURL
  :description: The URL that users use to access Mattermost. The port number is required if it’s not a standard port, such as 80 or 443.

Site URL
~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+---------------------------------------------------------------+---------------------------------------------------------------+
| The URL that users use to access Mattermost.                  | - System Config path: **Environment > Web Server**            |
| The port number is required if it’s not a standard port,      | - ``config.json`` setting: ``.ServiceSettings.SiteURL",``     |
| such as 80 or 443. This field is required.                    | - Environment variable: ``MM_SERVICESETTINGS_SITEURL``        |
|                                                               |                                                               |
| Select the **Test Live URL** button in the System Console     |                                                               |
| to validate the Site URL.                                     |                                                               |
+---------------------------------------------------------------+---------------------------------------------------------------+
| **Notes**:                                                                                                                    |
|                                                                                                                               |
| - The URL may contain a subpath, such as ``https://example.com/company/mattermost``.                                          |
| - If you change the Site URL value, log out of the Desktop App, and sign back in using the new domain.                        |
| - If Site URL is not set:                                                                                                     |
|                                                                                                                               |
|   - Email notifications will contain broken links, and email batching will not work.                                          |
|   - Authentication via OAuth 2.0, including GitLab, Google, and Entra ID, will fail.                                          |
|   - Plugins may not work as expected.                                                                                         |
+-------------------------------------------------------------------------------------------------------------------------------+

.. config:setting:: web-listenaddress
  :displayname: Web server listen address (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.ListenAddress
  :environment: MM_SERVICESETTINGS_LISTENADDRESS

  The address and port to which to bind and listen. Specifying ``:8065`` will bind to all network interfaces.
  Specifying ``127.0.0.1:8065`` will only bind to the network interface having that IP address.

Web server listen address
~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+---------------------------------------------------------------+------------------------------------------------------------------+
| The address and port to which to bind and listen.             | - System Config path: **Environment > Web Server**               |
| Specifying ``:8065`` will bind to all network interfaces.     | - ``config.json`` setting: ``".ServiceSettings.ListenAddress",`` |
| Specifying ``127.0.0.1:8065`` will only bind to the network   | - Environment variable: ``MM_SERVICESETTINGS_LISTENADDRESS``     |
| interface having that IP address.                             |                                                                  |
|                                                               |                                                                  |
| If you choose a port of a lower level (called “system ports”  |                                                                  |
| or “well-known ports”, in the range of 0-1023), you must have |                                                                  |
| permissions to bind to that port.                             |                                                                  |
+---------------------------------------------------------------+------------------------------------------------------------------+

.. config:setting:: web-forwardinsecure
  :displayname: Forward port 80 to 443 (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.Forward80To443
  :environment: MM_SERVICESETTINGS_FORWARD80TO443

  - **true**: Forwards all insecure traffic from port 80 to secure port 443.
  - **false**: **(Default)** When using a proxy such as NGINX in front of Mattermost this setting is unnecessary and should be set to false.

Forward port 80 to 443
~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+---------------------------------------------------------------+--------------------------------------------------------------------------+
| Forward insecure traffic from port 80 to port 443.            | - System Config path: **Environment > Web Server**                       |
|                                                               | - ``config.json`` setting: ``".ServiceSettings.Forward80To443: false",`` |
| - **true**: Forwards all insecure traffic from port 80 to     | - Environment variable: ``MM_SERVICESETTINGS_FORWARD80TO443``            |
|   secure port 443.                                            |                                                                          |
| - **false**: **(Default)** When using a proxy such as NGINX   |                                                                          |
|   in front of Mattermost this setting is unnecessary          |                                                                          |
|   and should be set to false.                                 |                                                                          |
+---------------------------------------------------------------+--------------------------------------------------------------------------+

.. config:setting:: web-connectionsecurity
  :displayname: Web server connection security (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.ConnectionSecurity
  :environment: MM_SERVICESETTINGS_CONNECTIONSECURITY
  :description: Connection security between Mattermost clients and the server.

  - **Not specified**: Mattermost will connect over an unsecure connection.
  - **TLS**: Encrypts the communication between Mattermost clients and your server.

Web server connection security
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+-----------------------------------------------------------------------+-----------------------------------------------------------------------+
| Connection security between Mattermost clients and the server.        | - System Config path: **Environment > Web Server**                    |
|                                                                       | - ``config.json`` setting: ``".ServiceSettings.ConnectionSecurity",`` |
| - **Not specified**: Mattermost will connect over an unsecure         | - Environment variable: ``MM_SERVICESETTINGS_CONNECTIONSECURITY``     |
|   connection.                                                         |                                                                       |
| - **TLS**: Encrypts the communication between Mattermost              |                                                                       |
|   clients and your server. See the :doc:`configuring TLS on           |                                                                       |
|   Mattermost </install/config-tls-mattermost>` for more details.      |                                                                       |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------+

.. config:setting:: web-tlscertificatefile
  :displayname: TLS certificate file (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.TLSCertFile
  :environment: MM_SERVICESETTINGS_TLSCERTFILE
  :description: The path to the certificate file to use for TLS connection security.

TLS certificate file
~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+------------------------------------------------------------------+
| The path to the certificate file to use for TLS        | - System Config path: **Environment > Web Server**               |
| connection security.                                   | - ``config.json`` setting: ``".ServiceSettings.TLSCertFile",``   |
|                                                        | - Environment variable: ``MM_SERVICESETTINGS_TLSCERTFILE``       |
| String input.                                          |                                                                  |
+--------------------------------------------------------+------------------------------------------------------------------+

.. config:setting:: web-tlskeyfile
  :displayname: TLS key file (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.TLSKeyFile
  :environment: MM_SERVICESETTINGS_TLSKEYFILE
  :description: The path to the TLS key file to use for TLS connection security.

TLS key file
~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+---------------------------------------------------------------+
| The path to the TLS key file to use for TLS            | - System Config path: **Environment > Web Server**            |
| connection security.                                   | - ``config.json`` setting: ``".ServiceSettings.TLSKeyFile",`` |
|                                                        | - Environment variable: ``MM_SERVICESETTINGS_TLSKEYFILE``     |
| String input.                                          |                                                               |
+--------------------------------------------------------+---------------------------------------------------------------+

.. config:setting:: web-useletsencrypt
  :displayname: Use Let's Encrypt (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.UseLetsEncrypt
  :environment: MM_SERVICESETTINGS_USELETSENCRYPT
  :description: Enable the automatic retrieval of certificates from Let’s Encrypt.

  - **true**: The certificate will be retrieved when a client attempts to connect from a new domain. This will work with multiple domains.
  - **false**: **(Default)** Manual certificate specification based on the TLS Certificate File and TLS Key File specified above.

Use Let's Encrypt
~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------+
| Enable the automatic retrieval of certificates from Let’s Encrypt.                            | - System Config path: **Environment > Web Server**                       |
| See the :doc:`configuring TLS on Mattermost documentation </install/config-tls-mattermost>`   | - ``config.json`` setting: ``".ServiceSettings.UseLetsEncrypt: false",`` |
| for more details on setting up Let’s Encrypt.                                                 | - Environment variable: ``MM_SERVICESETTINGS_USELETSENCRYPT``            |
|                                                                                               |                                                                          |
| - **true**: The certificate will be retrieved when a client                                   |                                                                          |
|   attempts to connect from a new domain. This will work with                                  |                                                                          |
|   multiple domains.                                                                           |                                                                          |
| - **false**: **(Default)** Manual certificate specification                                   |                                                                          |
|   based on the TLS Certificate File and TLS Key File specified                                |                                                                          |
|   above.                                                                                      |                                                                          |
+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------+

.. config:setting:: web-letsencryptcache
  :displayname: Let's Encrypt certificate cache file (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.LetsEncryptCertificateCacheFile
  :environment: MM_SERVICESETTINGS_LETSENCRYPTCERTIFICATECACHEFILE
  :description: The path to the file where certificates and other data about the Let’s Encrypt service will be stored.

Let's Encrypt certificate cache file
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+------------------------------------------------------------------------------------+
| The path to the file where certificates and other data | - System Config path: **Environment > Web Server**                                 |
| about the Let’s Encrypt service will be stored.        | - ``config.json`` setting: ``".ServiceSettings.LetsEncryptCertificateCacheFile",`` |
|                                                        | - Environment variable: ``MM_SERVICESETTINGS_LETSENCRYPTCERTIFICATECACHEFILE``     |
| File path input.                                       |                                                                                    |
+--------------------------------------------------------+------------------------------------------------------------------------------------+

.. config:setting:: web-readtimeout
  :displayname: Read timeout (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.ReadTimeout
  :environment: MM_SERVICESETTINGS_READTIMEOUT
  :description: Maximum time allowed from when the connection is accepted to when the request body is fully read. Default is **300** seconds.

Read timeout
~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+---------------------------------------------------------+---------------------------------------------------------------------+
| Maximum time allowed from when the connection is        | - System Config path: **Environment > Web Server**                  |
| accepted to when the request body is fully read.        | - ``config.json`` setting: ``".ServiceSettings.ReadTimeout: 300",`` |
|                                                         | - Environment variable: ``MM_SERVICESETTINGS_READTIMEOUT``          |
| Numerical input in seconds. Default is **300** seconds. |                                                                     |
+---------------------------------------------------------+---------------------------------------------------------------------+

.. config:setting:: web-writetimeout
  :displayname: Write timeout (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.WriteTimeout
  :environment: MM_SERVICESETTINGS_WRITETIMEOUT

  If using HTTP (insecure), this is the maximum time, in seconds, allowed from the end of reading the request headers until the response is written.
  If using HTTPS, it's the total time, in seconds, from when the connection is accepted until the response is written.
  Default is 300 seconds.

Write timeout
~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+----------------------------------------------------------+-----------------------------------------------------------------------------+
| - If using HTTP (insecure), this is the maximum time     | - System Config path: **Environment > Web Server**                          |
|   allowed from the end of reading the request headers    | - ``config.json`` setting: ``".ServiceSettings.WriteTimeout: 300",``        |
|   until the response is written.                         | - Environment variable: ``MM_SERVICESETTINGS_WRITETIMEOUT``                 |
| - If using HTTPS, it's the total time from when the      |                                                                             |
|   connection is accepted until the response is written.  |                                                                             |
|                                                          |                                                                             |
| Numerical input in seconds. Default is **300** seconds.  |                                                                             |
+----------------------------------------------------------+-----------------------------------------------------------------------------+

.. config:setting:: web-idletimeout
  :displayname: Idle timeout (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.IdleTimeout
  :environment: MM_SERVICESETTINGS_IDLETIMEOUT
  :description: This is the maximum time, in seconds, allowed before an idle connection is disconnected. Default is **300** seconds.

Idle timeout
~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+---------------------------------------------------------+---------------------------------------------------------------------+
| Set an explicit idle timeout in the HTTP server.        | - System Config path: **Environment > Web Server**                  |
| This is the maximum time allowed before an idle         | - ``config.json`` setting: ``".ServiceSettings.IdleTimeout: 300",`` |
| connection is disconnected.                             | - Environment variable: ``MM_SERVICESETTINGS_IDLETIMEOUT``          |
|                                                         |                                                                     |
| Numerical input in seconds. Default is **300** seconds. |                                                                     |
+---------------------------------------------------------+---------------------------------------------------------------------+

.. config:setting:: web-webservermode
  :displayname: Webserver mode (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.WebserverMode
  :environment: MM_SERVICESETTINGS_WEBSERVERMODE

  - **gzip**: **(Default)** The Mattermost server will serve static files compressed with gzip to improve performance.
  - **Uncompressed**: The Mattermost server will serve static files uncompressed.
  - **Disabled**: The Mattermost server will not serve static files.

Webserver mode
~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+---------------------------------------------------------------------+------------------------------------------------------------------------+
| We recommend gzip to improve performance unless your                | - System Config path: **Environment > Web Server**                     |
| environment has specific restrictions, such as a web proxy that     | - ``config.json`` setting: ``".ServiceSettings.WebserverMode: gzip",`` |
| distributes gzip files poorly.                                      | - Environment variable: ``MM_SERVICESETTINGS_WEBSERVERMODE``           |
|                                                                     |                                                                        |
| - **gzip**: **(Default)** The Mattermost server will serve static   |                                                                        |
|   files compressed with gzip to improve performance.                |                                                                        |
|   gzip compression applies to the HTML, CSS, Javascript, and other  |                                                                        |
|   static content files that make up the Mattermost web client.      |                                                                        |
| - **Uncompressed**: The Mattermost server will serve static         |                                                                        |
|   files uncompressed.                                               |                                                                        |
| - **Disabled**: The Mattermost server will not serve static files.  |                                                                        |
+---------------------------------------------------------------------+------------------------------------------------------------------------+

.. config:setting:: web-insecureoutgoingconnections
  :displayname: Enable insecure outgoing connections (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.EnableInsecureOutgoingConnections
  :environment: MM_SERVICESETTINGS_ENABLEINSECUREOUTGOINGCONNECTIONS

  - **true**: Outgoing HTTPS requests, including S3 clients, can accept unverified, self-signed certificates.
  - **false**: **(Default)** Only secure HTTPS requests are allowed.

Enable insecure outgoing connections
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+---------------------------------------------------------------+---------------------------------------------------------------------------------------------+
| Configure Mattermost to allow insecure outgoing connections.  | - System Config path: **Environment > Web Server**                                          |
|                                                               | - ``config.json`` setting: ``".ServiceSettings.EnableInsecureOutgoingConnections: false",`` |
| - **true**: Outgoing HTTPS requests, including S3 clients,    | - Environment variable: ``MM_SERVICESETTINGS_ENABLEINSECUREOUTGOINGCONNECTIONS``            |
|   can accept unverified, self-signed certificates.            |                                                                                             |
|   For example, outgoing webhooks to a server with a           |                                                                                             |
|   self-signed TLS certificate, using any domain, will be      |                                                                                             |
|   allowed, and will skip TLS verification.                    |                                                                                             |
| - **false**: **(Default)** Only secure HTTPS requests are     |                                                                                             |
|   allowed.                                                    |                                                                                             |
+---------------------------------------------------------------+---------------------------------------------------------------------------------------------+
| **Security note**: Enabling this feature makes these connections susceptible to man-in-the-middle attacks.                                                  |
+---------------------------------------------------------------+---------------------------------------------------------------------------------------------+

.. config:setting:: web-managedresourcepaths
  :displayname: Managed resource paths (Web Server)
  :systemconsole: Environment > Web Server
  :configjson: .ServiceSettings.ManagedResourcePaths
  :environment: MM_SERVICESETTINGS_MANAGEDRESOURCEPATHS
  :description: A comma-separated list of paths within the Mattermost domain that are managed by a third party service instead of Mattermost itself.

Managed resource paths
~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+-------------------------------------------------------------------------+
| A comma-separated list of paths within the Mattermost  | - System Config path: **Environment > Web Server**                      |
| domain that are managed by a third party service       | - ``config.json`` setting: ``".ServiceSettings.ManagedResourcePaths",`` |
| instead of Mattermost itself.                          | - Environment variable: ``MM_SERVICESETTINGS_MANAGEDRESOURCEPATHS``     |
|                                                        |                                                                         |
| Links to these paths will be opened in a new           |                                                                         |
| tab/window by Mattermost apps.                         |                                                                         |
|                                                        |                                                                         |
| For example, if Mattermost is running on               |                                                                         |
| ``https://mymattermost.com``, setting this to          |                                                                         |
| conference will cause links such as                    |                                                                         |
| ``https://mymattermost.com/conference`` to open in a   |                                                                         |
| new window.                                            |                                                                         |
+--------------------------------------------------------+-------------------------------------------------------------------------+
| **Note:**                                                                                                                        |
| When using the Mattermost Desktop App, additional configuration is required to open the link within the Desktop App instead of   |
| in a browser. See the :doc:`desktop managed resources </install/desktop-app-managed-resources>`                                  |
| documentation for details.                                                                                                       |
+--------------------------------------------------------+-------------------------------------------------------------------------+

Reload configuration from disk
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+----------------------------------------------------------+---------------------------------------------------------------+
| You must change the database line in the ``config.json`` | - System Config path: **Environment > Web Server**            |
| file, and then reload configuration to fail over         | - ``config.json`` setting: N/A                                |
| without taking the server down.                          | - Environment variable: N/A                                   |
|                                                          |                                                               |
| Select the **Reload configuration from disk** button     |                                                               |
| in the System Console after changing your database       |                                                               |
| configuration. Then, go to **Environment > Database**    |                                                               |
| and select **Recycle Database Connections** to           |                                                               |
| complete the reload.                                     |                                                               |
+----------------------------------------------------------+---------------------------------------------------------------+

Purge all caches
~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+----------------------------------------------------------+---------------------------------------------------------------+
| Purge all in-memory caches for sessions, accounts,       | - System Config path: **Environment > Web Server**            |
| and channels.                                            | - ``config.json`` setting: N/A                                |
|                                                          | - Environment variable: N/A                                   |
| Select the **Purge All Caches** button in the System     |                                                               |
| Console to purge all caches.                             |                                                               |
+----------------------------------------------------------+---------------------------------------------------------------+
| **Note**: Purging the caches may adversely impact performance.                                                           |
| :doc:`high availability cluster-based deployments </scale/high-availability-cluster-based-deployment>` will attempt      |
| to purge all the servers in the cluster                                                                                  |
+----------------------------------------------------------+---------------------------------------------------------------+

.. config:setting:: web-websocketurl
  :displayname: Websocket URL (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.WebsocketURL
  :environment: MM_SERVICESETTINGS_WEBSOCKETURL
  :description: You can configure the server to instruct clients on where they should try to connect websockets to.

Websocket URL
~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+---------------------------------------------------------------------+
| You can configure the server to instruct clients       | - System Config path: N/A                                           |
| on where they should try to connect websockets to.     | - ``config.json`` setting: ``".ServiceSettings.WebsocketURL: "",``  |
|                                                        | - Environment variable: ``MM_SERVICESETTINGS_WEBSOCKETURL``         |
| String input.                                          |                                                                     |
+--------------------------------------------------------+---------------------------------------------------------------------+
| **Note**: We strongly recommend configuring a single websocket URL that matches the `Site URL <#site-url>`_ configuration    |
| setting.                                                                                                                     |
+--------------------------------------------------------+---------------------------------------------------------------------+

.. config:setting:: web-licensefilelocation
  :displayname: License file location (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.LicenseFileLocation
  :environment: MM_SERVICESETTINGS_LICENSEFILELOCATION
  :description: The path and filename of the license file on disk.

License file location
~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+----------------------------------------------------------------------------+
| The path and filename of the license file on disk.     | - System Config path: N/A                                                  |
| On startup, if Mattermost can't find a valid license   | - ``config.json`` setting: ``".ServiceSettings.LicenseFileLocation: "",``  |
| in the database from a previous upload, it looks in    | - Environment variable: ``MM_SERVICESETTINGS_LICENSEFILELOCATION``         |
| this path for the license file.                        |                                                                            |
|                                                        |                                                                            |
| String input. Can be an absolute path or a path        |                                                                            |
| relative to the ``mattermost`` directory.              |                                                                            |
+--------------------------------------------------------+----------------------------------------------------------------------------+

.. config:setting:: web-tlsminimumversion
  :displayname: TLS minimum version (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.TLSMinVer
  :environment: MM_SERVICESETTINGS_TLSMINVER
  :description: The minimum TLS version used by the Mattermost server. Default value is **1.2**.

TLS minimum version
~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+---------------------------------------------------------------------+
| The minimum TLS version used by the Mattermost server. | - System Config path: N/A                                           |
|                                                        | - ``config.json`` setting: ``".ServiceSettings.TLSMinVer: 1.2",``   |
| String input. Default is **1.2**.                      | - Environment variable: ``MM_SERVICESETTINGS_TLSMINVER``            |
+--------------------------------------------------------+---------------------------------------------------------------------+
| **Note**: This setting only takes effect if you are using the built-in server binary directly, and not using a reverse proxy |
| layer, such as NGINX.                                                                                                        |
+--------------------------------------------------------+---------------------------------------------------------------------+

.. config:setting:: web-trustedproxyipheader
  :displayname: Trusted proxy IP header (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.TrustedProxyIPHeader
  :environment: MM_SERVICESETTINGS_TRUSTEDPROXYIPHEADER
  :description: Specified headers that will be checked, one by one, for IP addresses (order is important). All other headers are ignored.

Trusted proxy IP header
~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+------------------------------------------------------------------------------+
| Specified headers that will be checked, one by one,    | - System Config path: N/A                                                    |
| for IP addresses (order is important).                 | - ``config.json`` setting: ``".ServiceSettings.TrustedProxyIPHeader: []",``  |
| All other headers are ignored.                         | - Environment variable: ``MM_SERVICESETTINGS_TRUSTEDPROXYIPHEADER``          |
|                                                        |                                                                              |
| String array input consisting of header names,         |                                                                              |
| such as ``["X-Forwarded-For", "X-Real-Ip"]``.          |                                                                              |
+--------------------------------------------------------+------------------------------------------------------------------------------+
| **Notes**:                                                                                                                            |
|                                                                                                                                       |
| - The default value of ``[]`` means that no header will be trusted. Prior to v5.12, the absence of this configuration setting entry   |
|   will have it set to ``["X-Forwarded-For", "X-Real-Ip"]`` on upgrade to maintain backwards compatibility.                            |
| - We recommend keeping the default setting when Mattermost is running without a proxy to avoid the client sending the headers and     |
|   bypassing rate limiting and/or the audit log.                                                                                       |
| - For environments that use a reverse proxy, this issue does not exist, provided that the headers are set by the reverse proxy.       |
|   In those environments, only explicitly whitelist the header set by the reverse proxy and no additional values.                      |
|                                                                                                                                       |
|                                                                                                                                       |
+--------------------------------------------------------+------------------------------------------------------------------------------+

.. config:setting:: web-enablehsts
  :displayname: Enable Strict Transport Security (HSTS) (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.TLSStrictTransport
  :environment: MM_SERVICESETTINGS_TLSSTRICTTRANSPORT

  - **true**: Adds the Strict Transport Security (HSTS) header to all responses, forcing the browser to request all resources via HTTPS.
  - **false**: **(Default)** No restrictions on TLS transport. Strict Transport Security (HSTS) header isn't added to responses.

Enable Strict Transport Security (HSTS)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+-------------------------------------------------------------------------------+
| - **true**: Adds the Strict Transport Security (HSTS)  | - System Config path: N/A                                                     |
|   header to all responses, forcing the browser to      | - ``config.json`` setting: ``".ServiceSettings.TLSStrictTransport: false",``  |
|   request all resources via HTTPS.                     | - Environment variable: ``MM_SERVICESETTINGS_TLSSTRICTTRANSPORT``             |
| - **false**: **(Default)** No restrictions on TLS      |                                                                               |
|   transport. Strict Transport Security (HSTS) header   |                                                                               |
|   isn't added to responses.                            |                                                                               |
+--------------------------------------------------------+-------------------------------------------------------------------------------+
| See the `Strict-Transport-Security <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security>`__            |
| documentation for details.                                                                                                             |
+--------------------------------------------------------+-------------------------------------------------------------------------------+

.. config:setting:: web-securetlstransportexpiry
  :displayname: Secure TLS transport expiry (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.TLSStrictTransportMaxAge
  :environment: MM_SERVICESETTINGS_TLSSTRICTTRANSPORTMAXAGE
  :description: The time, in seconds, that the browser remembers a site is only to be accessed using HTTPS. Default is **63072000** seconds (2 years).

Secure TLS transport expiry
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+----------------------------------------------------------------------------------------+
| The time, in seconds, that the browser remembers a     | - System Config path: N/A                                                              |
| site is only to be accessed using HTTPS. After this    | - ``config.json`` setting: ``".ServiceSettings.TLSStrictTransportMaxAge: 63072000",``  |
| period, a site can't be accessed using HTTP unless     | - Environment variable: ``MM_SERVICESETTINGS_TLSSTRICTTRANSPORTMAXAGE``                |
| ``TLSStrictTransport`` is set to ``true``.             |                                                                                        |
|                                                        |                                                                                        |
| Numerical input. Default is **63072000** (2 years).    |                                                                                        |
+--------------------------------------------------------+----------------------------------------------------------------------------------------+
| See the `Strict-Transport-Security <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security>`__                     |
| documentation for details.                                                                                                                      |
+--------------------------------------------------------+----------------------------------------------------------------------------------------+

.. config:setting:: web-tlscipheroverwrites
  :displayname: TLS cipher overwrites (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.TLSOverwriteCiphers
  :environment: MM_SERVICESETTINGS_TLSOVERWRITECIPHERS
  :description: Set TLS ciphers overwrites to meet requirements from legacy clients which don't support modern ciphers, or to limit the types of accepted ciphers.

TLS cipher overwrites
~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+-----------------------------------------------------------------------------+
| Set TLS ciphers overwrites to meet requirements from   | - System Config path: N/A                                                   |
| legacy clients which don't support modern ciphers,     | - ``config.json`` setting: ``".ServiceSettings.TLSOverwriteCiphers: []",``  |
| or to limit the types of accepted ciphers.             | - Environment variable: ``MM_SERVICESETTINGS_TLSOVERWRITECIPHERS``          |
|                                                        |                                                                             |
| If none specified, the Mattermost server assumes a     |                                                                             |
| set of currently considered secure ciphers, and allows |                                                                             |
| overwrites in the edge case.                           |                                                                             |
|                                                        |                                                                             |
| String array input.                                    |                                                                             |
+--------------------------------------------------------+-----------------------------------------------------------------------------+
| **Notes**:                                                                                                                           |
|                                                                                                                                      |
| - This setting only takes effect if you are using the built-in server binary directly, and not using a reverse proxy layer, such     |
|   as NGINX.                                                                                                                          |
| - See the ``ServerTLSSupportedCiphers`` variable in `/model/config.go                                                                |
|   <https://github.com/mattermost/mattermost/blob/master/server/public/model/config.go>`__ for a list of ciphers considered secure.   |
+--------------------------------------------------------+-----------------------------------------------------------------------------+

.. config:setting:: web-goroutinehealththreshold
  :displayname: Goroutine health threshold (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.GoroutineHealthThreshold
  :environment: MM_SERVICESETTINGS_GOROUTINEHEALTHTHRESHOLD
  :description: Set a threshold on the number of goroutines when the Mattermost system is considered to be in a healthy state. Default is **-1** which turns off checking for the threshold.

Goroutine health threshold
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+----------------------------------------------------------------------------------+
| Set a threshold on the number of goroutines when the   | - System Config path: N/A                                                        |
| Mattermost system is considered to be in a healthy     | - ``config.json`` setting: ``".ServiceSettings.GoroutineHealthThreshold: -1",``  |
| state.                                                 | - Environment variable: ``MM_SERVICESETTINGS_GOROUTINEHEALTHTHRESHOLD``          |
|                                                        |                                                                                  |
| When goroutines exceed this limit, a warning is        |                                                                                  |
| returned in the server logs.                           |                                                                                  |
|                                                        |                                                                                  |
| Numeric input. Default is **-1** which turns off       |                                                                                  |
| checking for the threshold.                            |                                                                                  |
+--------------------------------------------------------+----------------------------------------------------------------------------------+

.. config:setting:: web-allowcookiesforsubdomains
  :displayname: Allow cookies for subdomains (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.AllowCookiesForSubdomains
  :environment: MM_SERVICESETTINGS_ALLOWCOOKIESFORSUBDOMAINS

  - **true**: **(Default)** Allows cookies for subdomains by setting the domain parameter on Mattermost cookies.
  - **false**: Cookies not allowed for subdomains.

Allow cookies for subdomains
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E10 or E20</p>

+--------------------------------------------------------+-------------------------------------------------------------------------------------+
| - **true**: **(Default)** Allows cookies for           | - System Config path: N/A                                                           |
|   subdomains by setting the domain parameter on        | - ``config.json`` setting: ``".ServiceSettings.AllowCookiesForSubdomains: true",``  |
|   Mattermost cookies.                                  | - Environment variable: ``MM_SERVICESETTINGS_ALLOWCOOKIESFORSUBDOMAINS``            |
| - **false**: Cookies not allowed for subdomains.       |                                                                                     |
+--------------------------------------------------------+-------------------------------------------------------------------------------------+

.. config:setting:: web-clusterlogtimeout
  :displayname: Cluster log timeout (Web Server)
  :systemconsole: N/A
  :configjson: .ServiceSettings.ClusterLogTimeoutMilliseconds
  :environment: MM_SERVICESETTINGS_CLUSTERLOGTIMEOUTMILLISECONDS
  :description: Define the frequency, in milliseconds, of cluster request time logging for performance monitoring. Default is **2000** milliseconds (2 seconds).

Cluster log timeout
~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

.. raw:: html

 <p class="mm-label-note">Also available in legacy Mattermost Enterprise Edition E20</p>

+--------------------------------------------------------+-----------------------------------------------------------------------------------------+
| Define the frequency, in milliseconds, of cluster      | - System Config path: N/A                                                               |
| request time logging for performance monitoring.       | - ``config.json`` setting: ``".ServiceSettings.ClusterLogTimeoutMilliseconds: 2000",``  |
|                                                        | - Environment variable: ``MM_SERVICESETTINGS_CLUSTERLOGTIMEOUTMILLISECONDS``            |
|                                                        |                                                                                         |
| Numerical input. Default is **2000** milliseconds      |                                                                                         |
| (2 seconds).                                           |                                                                                         |
+--------------------------------------------------------+-----------------------------------------------------------------------------------------+
| See the :doc:`performance monitoring </scale/deploy-prometheus-grafana-for-performance-monitoring>` documentation for details.                   |
+--------------------------------------------------------+-----------------------------------------------------------------------------------------+

.. config:setting:: file-maxpayloadsize
  :displayname: Maximum payload size (File Storage)
  :systemconsole: N/A
  :configjson: .FileSettings.MaximumPayloadSizeBytes
  :environment: MM_FILESETTINGS_MAXIMUMPAYLOADSIZEBYTES
  :description: The maximum payload size in bytes for all APIs except APIs that receive a file as an input. For example, the upload attachment API or the API to upload a custom emoji. Default is 300000.

Maximum payload size
~~~~~~~~~~~~~~~~~~~~

+-----------------------------------------------------------+----------------------------------------------------------------------------------+
| The maximum payload size in bytes for all APIs except     | - System Config path: N/A                                                        |
| APIs that receive a file as an input.                     | - ``config.json`` setting: ``".FileSettings.MaximumPayloadSizeBytes: 300000",``  |
|                                                           | - Environment variable: ``MM_FILESETTINGS_MAXIMUMPAYLOADSIZEBYTES``              |
| For example, the upload attachment API or the API to      |                                                                                  |
| upload a custom emoji.                                    |                                                                                  |
|                                                           |                                                                                  |
| Numerical value. Default is **300000** (300 kB).          |                                                                                  |
+-----------------------------------------------------------+----------------------------------------------------------------------------------+

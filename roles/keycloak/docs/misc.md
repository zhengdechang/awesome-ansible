#### More verbose logging

1. Sudo as the keycloak user

```
sudo -iu keycloak
```

2. Edit the JBoss configuration file

```
vim current/standalone/configuration/standalone.xml
```

3. Above `<root-logger>`

```xml
            <!-- Log unencrypted SAML responses -->
            <logger category="org.apache.xml.security.encryption.XMLCipher">
                <level name="DEBUG"/>
            </logger>
            <logger category="org.keycloak.events">
                <level name="DEBUG"/>
            </logger>
            <logger category="org.keycloak.protocol.oidc">
                <level name="DEBUG"/>
            </logger>
            <logger category="org.keycloak.saml">
                <level name="DEBUG"/>
            </logger>
```

4. Restart keycloak

```
sudo systemctl restart keycloak
```

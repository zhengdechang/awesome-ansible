1. Get the metadata for the Keycloak SAML IdP

    The Keycloak IdP metadata is available from one of the following URLs:

    http://hostname:8080/auth/realms/master/protocol/saml/descriptor
    https://hostname:8443/auth/realms/master/protocol/saml/descriptor

    (Replace hostname with the hostname of your Keycloak server)

2. Configure the SP with the Keycloak IdP metadata and entity ID

    See the documentation for your SP implementation

3. Get the metadata for the SP

4. Add the SP as a client in Keycloak

    1. *Clients* > *Create*

    2. *Import* > *Select file* > select the SP metadata file > *Save*

5. Import the SP cert into Keycloak

    This must be done because it isn't automatically done when importing the metadata

    1. Get the public SP cert. If you don't have an easy way to get it, you can get it from the metadata:

        1. Copy the content between the `<ds:X509Certificate>` and `</ds:X509Certificate>` tags

        2. Paste it into a new file

        3. Add a new line containing `-----BEGIN CERTIFICATE-----` at the top of the file

        4. Add a new line containing `-----END CERTIFICATE-----` at the bottom of the file

    2. In Keycloak, go to *Clients* > the client you created > *SAML Keys* > *Import*

    3. Change *Archive Format* as needed (change it to *Certificate PEM* if you're using the certificate from the metadata as described above)

    4. *Import File* > *Select file* > select the SP cert file > *Import*

6. Configure attributes to release to the SP

    1. In Keycloak, go to *Clients* > the client you created > *Mappers*

    2. Click *Create* to create new mappers or *Add Builtin* to create new mappers

        An example of creating a new mapper:

        - *Mapper Type*: *User Property*

        - *Property*: email (this needs to match the *User Model Attribute* in the mapper for your LDAP user federation)

        - *Friendly Name*: mail

        - *SAML Attribute Name*: urn:oid:0.9.2342.19200300.100.1.3

        - *SAML Attribute NameFormat*: as appropriate (choose *URI Reference* for Shibboleth SP)

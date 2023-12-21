1. Get the metadata URL of the external SAML IdP you wish to broker

2. Configure the external IdP in Keycloak
    1. *Identity Providers* > *Add provider* > *SAML v2.0*

    2. Set an *Alias* as desired

    3. *Import from URL* > enter the URL of the metadata for the external SAML IdP you wish to broker > *Import*

    4. If the external IdP is a Shibboleth IdP, set the following settings to match the Shibboleth IdP defaults:
        1. *Want AuthnRequests Signed* > *On*

        2. *Want Assertions Encrypted* > *On*

    5. *Save*

3. Map attributes
    1. In Keycloak, go to *Identity Providers* > the external IdP you configured > *Mappers* > *Create*

        *Mapper Type* > *Attribute Importer*
        *Name* > *givenName*
        *Friendly Name* > *givenName*
        *User Attribute Name* > *firstName*

    sn > lastName
    mail > email
    username, Username Template Importer, `${ATTRIBUTE.mail}`

Active Directory
- http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress
- http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname
- http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname

4. Configure
    1. In Keycloak, go to *Identity Providers* > the external IdP you configured > *Export*

    2. Download the metadata and use it to configure Keycloak as an SP in the external IdP you wish to broker





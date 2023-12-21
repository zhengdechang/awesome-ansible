1. Configure a new LDAP user federation provider

    1. *Configure* > *User Federation*

    2. *Add provider* > *ldap*

    3. *Vendor* > *Active Directory*

    4. Configure the following properties as needed
        - *Edit Mode*
        - *Connection URL*
        - *Users DN*
        - *Bind DN*
        - *Bind Credential*

    5. *Save*

2. (Optional) Create a mapping for first name

    1. *Configure* > *User Federation* > Active Directory provider

    2. *Mappers* > *Create*

    3. *Name* > first name

    4. *Mapper Type* > *user-attribute-ldap-mapper*

    5. *User Model Attribute* > firstName

    6. *LDAP Attribute* > givenName

    7. *Always Read Value From LDAP* > enable if desired

    8. *Save*

3. Create a new group mapper

    1. *Configure* > *User Federation* > Active Directory provider

    2. *Mappers* > *Create*

    3. *Mapper Type* > *group-ldap-mapper*

    4. Configure the following properties as needed
        - *Name*
        - *Preserve Group Inheritance*
        - *LDAP Filter*

    5. *Save*

4. To map a user to a role in Keycloak

    1. The user must log in at least one time so she gets populated in Keycloak

    2. *Manage* > *Users*

    3. Search for the specific user or click *View all users*

    4. Click the *ID* of the user you'd like to edit

    5. *Role Mappings*

    6. In *Available Roles* select the desired role > *Add selected >*

4. To map a group

    1. At least one person from that group should log in so the group gets populated in Keycloak

    2. *Manage* > *Groups*

    3. Click the particular group you'd like to modify > *Edit*

    4. *Role Mappings*

    5. In *Available Roles* select the desired role > *Add selected >*

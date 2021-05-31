<h1 style="text-align: Center;font-weight: bold;color:" >
Implement Azure Security(20-25%)
</h1>
<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Authentication and Authorization |
</h2> 
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>

**Note**: Before using any type of Authentication & Authorization Azure.
You must Register your app in Azure Active Directory in Enterprise Applications.

<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Notes !
</h3>

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AUTHORIZATION & AUTHENTICATIONS-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Whats the Difference?~>
</h4>

**Authentication** - The process of ensuring a user or service is who they say they are

**Authorization** - The process of limiting what an authenticated user has access to.


&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--OATH and OPENID-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Deep Dive into Oath~>
</h4>


OAuth 2.0 is the industry protocol for **Authentication**. It allows a user to grand limited access to its protected resourses usually with HTTP. OAth seperates the role of the client from the resource owner.**Use When** For rich client & modern app scenarios and RESTful web API access. There are 3 components with OAuth 2 authentication:

1. **Resource Owner**
   - Request service from app
   - Own the data and assigns access to resources

2. **Resource Server**
    - Resource or data resides here
    - Trust Authorization server to replay who has access to what

3. **Authorization Server**
    - Known as Identy Provider
    - Handls all aspects of user access information and trust

After registering your app, youll need to understand 3 components you'll be receiving:

1. **Application(Client) ID** - A unique identifier for your app

2. **Redirect URI** - A link you can use to direct reponses back to your application

3. **Scenario URIs** - Links you can use for specific scenarios such as Terms of Service, Privacy Statements.Etcs'


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Deep Dive into OpenID~>
</h4>

**OpenID Connect** (OIDC) is an authentication protocol based on the OAuth2 protocol (which is used for authorization). OIDC uses the standardized message flows from OAuth2 to provide identity services.

The design goal of OIDC is "making simple things simple and complicated things possible". OIDC lets developers authenticate their users across websites and apps without having to own and manage password files. This provides the app builder with a secure way to verify the identity of the person currently using the browser or native app that is connected to the application. **Use when** There is a need for user consent and for web sign in.


&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:pink;" >
|--SAS and RBAC--|
</h4>



<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Shared Access Signature~>
</h4>

**Shared Access Signature** or **SAS** is a URI that grants restricted access rights to Azure Storage resources. Providing a **Shared Access Signature** provides you to share your certain storage account resources but want to keep your Storage account key confidential. Azure Gives us 3 types of SAS:

1. **Account-level SAS** - It delegates access to resources in one or more storage services. You're able to delegate accesst to operations that apply to a given service, such as ``Get/Set Service properties`` and ``Get Service Stats``/ Youre also can delegate acces to read, wrtie, and delete operations on blob containers, tables, queues, and file shares that are not permitted with service SAS.
    

2. **Service-level SAS** - Delegates access to a resource in just one of the storage services: Blob, Queue, Table, or File service.

3. **User delegation SAS** -  A user delegation SAS is secured with Azure AD credentials. This type of SAS is supported for the Blob service only and can be used to grant access to containers and blobs.


<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Role-Based Access control~>
</h4>

**Azure RBAC** usees role assignements to apply sets of permissions to security principals. A security principal is ohject that represents a user, group, service principal, or managed identity that is defines in Azure Active Directory. A permission set can give a security principal a "coarse-grain" level of access such as read or write access to all of the data in a storage account or all the data in a container.



| Role           |  Description |
|:-|:-|
| Storage Blob Data Owner | Full Access to Blob Storage containers and data. This accesspermites the security principal to set the owner and item, and to modify the ACL of all items |
| Storage Blob Data Contributor | read,wirte, and delete access to Blob storage container sand blobs. This access does not permit the securty princicpal to set the ownership of an item, but it can modify the ACL of tiems that are owned by the security principal |
| Storage Blob Data Reader | Read and list Blob storage containers and blobs |

*Roles* such as Owner, Contributor, Reader, and Storage Account Contributor permit a security principal to manage a storage account, but do not provide access to the data within that account. However, these roles (excluding Reader) can obtain access to the storage keys, which can be used in various client tools to access the data.

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is ACL?~>
</h4>

**ACLs** give you the ability to apply "finer grain" level of access to directories and files. An **ACL** is a permission construct that contains a series of ACL entries. Each ACL entry associates security principal with an access level.ACL come in two categories:

1. **Access ACLs** - Provides access to an object. Files and directories both have **Access ACLs**

2. **Default ACLs** - Parent template for access to child objects and directories. Files DO NOT have default ACLs, however.

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| How are permissions evaluated?~>
</h4>

During security principal-based authorization, permissions are evaluated in the following order:

1. Azure role assignments are evauluated first and take priority over any ACL assignments

2. If the operation is fully authorized based on Azure role assignment, then ACLs are not evaluated at all.

3.  If the operation is not fully authorized, then ACLs are evaluated.

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:pink;" >
|--Centralizing Your configuration--|
</h4>


Azure App configurations allows for you to centralize and secure your applicaitons settings and features. key-value pairs you can point your application or processes to consistency in your cloud applications. Connecting it and using it depends on the API youll be using but the workflow is generally the same.

1. Connect your applicaitons to the App configurations Store
2. Configure your app to use the values from the configurations
It isnt just for apps.


There are 2 types of tiers:

|       | Free | Standard
|:-     |:- |:- |
|Resources per subscription | 1 | Unlimited |
| Storage per Resource] | 10MB | 1GB|
| Revision History|  7 Days| 30 Days  |
| Request Quota| 1k Per day | 20k Per hour|
| SLA| None | 99.9% availability|
| Security Functionality| MSFT Managed Encryption,HMAC or AAD Authentication,RBAC Support, Managed identities,Service Tages| Same as free tier but added Customer-Managed encrption keys, Supports for private link |
| Cost| Free | $1.20 USD per day plus overage char at $0.06 per 10k request limit|

There are 3 Values on Stage

1. **Key** : Serve as identifiers for key-values and used to store reteive corresponding values.
    - Microsoft recommends organizing keys in hierachical namespace by using some sort of delimiter " : " or " / "
    - App Configuration treats key as a whole, so it will not attemp to parse keys to figure out structure or enforce rules.
    - Keys are case sensitive, so if you place "car01" and "Car01", theyre considered diffrent objects
    - Keys can use any Unicode character except %. Names cannot only be "." or ".."
    - No Larger than 10 KB
2. **Value**:
    - Are unicode strings , use any Unicode character for values.

3. **Label**:  Provide an additional attribute that cna help separate key-value pairs that use the same Key.
     - Convenient method of creating variants of a key
    - you need to provide the label, by default theyre not required or added.

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| Security~>
</h4>

Youre able to use two methods for securing your App configuration.

1. **Access keys**

2. **Azure AD/ Manage identities** - Which can access RBAC
    - User
    - Group
    - Service Principal
    - Managed Identity

Type of **App Configuration Roles** you can give with Azure AD/ Managed Identities:

1. **App Configuration Data Owner** - Use this role to give read/write/delete access to App Configuration data. This does not grant access to the App Configuration resource.

2. **App Configuration Data Reader**: Use this role to give read access to App Configuration data. This does not grant access to the App Configuration resourse

3. **Contributor** - Use this role to manage the App Configuration resource. While the App configuration data can be accessed using access keys, this role does not gran direct access to the data using Azure AD

4. **Reader** Use this role to give read access to the App Configuration resource. This does not gran access to the resource's access ekys, nor to the data stored in App Configuration.



<!-----------------------------------SUBJECT------------------------------------------->
<h2 style="text-align: left;font-weight: bold;color:orange;text-decoration:underline" >
| Azure Key Vaults |
</h2> 
<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Test Tips !
</h3>

<!--------------Sub-SUBJECT------------------->
<h3 style="text-align: Right;font-weight: bold;color:lightgreen;" >
<~ Notes |
</h3>


&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE KEY VAULT-->|
</h4>

<!---Sub--Sub-Sub-SUBJECT--->
<h4 style="font-style:italic;font-weight: bold;color:lightblue;" >
| What is Azure Key Vault~>
</h4>


Azure Key Vault is the place where you can hide keys and sure only the people and services you trust can have access. When using Azure Key vault you can.

- Securely access keys , secrets , and certificates from your application or services without having to write the code yourself.
- Use keys for signing and encryption, but keep them external from your applications
- Store things like password

&emsp;
 <!----Sub-Sub-SUBJECT---->
<h4 style="text-align:center;font-weight: bold;color:Pink;" >
|<--AZURE KEY Certificates-->|
</h4>
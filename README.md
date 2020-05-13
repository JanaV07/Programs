# Programs
pending works

1.PPT 
Good Morning and Good Evening everyone - today we are here to discuss about designing multiple versions for our NXS NEXEN APIs.

Myself - Janarthanan Veeramani from NXS DEV

Lets Get in :

The following slide contains the Agenda of our today meeting.

The goal of this project is to improve the clients experience with our NEXEN APIs by introducing new schema for version control of APIs

The slide contains OOM Details of our project. the total hours will be 1540.

Slide has our Team details with business owner Kit, Product Owner Rodndey, Project manger Keith and the Development Manager Joan.

Today - 

We support different versions of messaging integration for Persing Business Services.
Such as 
	Legacy - XML formatted Messages
	and SOAP messages
	
	Also we have exposed 27 REST APIs in the NEXEN API Store 
	Among that 5 API has 2 versions V1 and V2. 
		V1 follows the SOAP Schema and V2 follows the Standard REST.
		Now V1 is hidden from the new usage 
 and the other 22 has 1 Standard REST version. 
 
On the whole each API has only one standard version.

Today discussion will introduce a new use cases focus on REST API schema versions as a change control mechanism

Since we are having one Standard version of the API, Whenever we have breaking changes at the back end systems, The clients are also required to implement the change at their end and tied to our Pershing release cycles.
 APIs like Account Services and AMPS with frequent changes add more diffuclties to this.

to overcome the difficulties - we will introudce Two Standard Versions.
vN and vN+1

and a deprecation schedule for the vN.

the following slide shows the USER model and key use Cases

For Example 2 clients consuming our API Version V1, later a new breaking change required for one of the consumer - which will lead to the new Version of the API V2. 

A grace period will be given for the other consumer to migrate to v2. Once he migrated V1 will be deprecated. 

and the same pattern continues.

The benifits will be
Client Flexibility
Reduce frequency of breaking releases

The slide will show in depth detail with te API Versioning :

Whenever we receive a breaking change - a new Version of API will be developed and the deprecation countdown will be triggered to the existing version.

the new changes will be updated only on vN+1 API.
below are the APIs targeted this year for new version

The slide has our current state architecture details about the clients, and the various systems.

The following slide shows the overall architecture of our NetXservices
7
The blue highlighted parts will be modified for this API Versioning and the new API will be exposed in a new GF domain nxs.bnymellon.net

The following slide shows the Data flow - The blue highlighted will be the new version which will be developed using spring boot in GF infrastructure.

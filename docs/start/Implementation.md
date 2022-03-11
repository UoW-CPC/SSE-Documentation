# SSE Implementation
SSE consists of three main parties: the SSE server, the SSE Trusted Authority and a demo SSE client. In addition, MinIO server and teep-server are optional components for SSE.

More specially, SSE client is a web application which uses SSE services such as uploading encrypted data, search/update/delete over the stored encrypted data. SSE server stores the encrypted data which is uploaded by the SSE client. It also provides the services such as search/update/delete over the store data. SSE Trusted Authority (SSE TA) stores the metadata which is used for generating the search/update/delete token (at the SSE client), and verifying the search/update/delete tokens on behalf of the SSE server. Apart from that, MinIO server stores encrypted binary large objects (blob), and teep-server provides SGX related services such as creating, installing SGX enclaves. These two components are optional. MinIO is only necessary when a client application wishes to support encrypting blob data and search/update/delete over its encrypted metadata. Meanwhile, teep-server is needed when we wish to enable SGX at SSE TA to increase the security level.

The list below shows the details of SSE components:

- [SSE Server](https://gitlab.com/asclepios-project/symmetric-searchable-encryption-server)
- [SSE Trusted Authority](https://gitlab.com/asclepios-project/sseta)
- [SSE Client](https://gitlab.com/asclepios-project/sseclient)
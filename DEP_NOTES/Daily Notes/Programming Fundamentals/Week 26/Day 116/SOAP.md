
taken from Yastih's note
## SOAP Architecture

![[Pasted image 20240814185750.png]]

### **WSDL (Web Services Description Language) File**

A WSDL file is an XML document that describes a web service. It contains information about the services' operations, messages, and protocols. This information is used by clients to interact with the web service.

### **UDDI Registry**

**UDDI** stands for **Universal Description, Discovery, and Integration**. It's essentially a global online directory of web services. Think of it as the Yellow Pages for web services.

WSDL file is given to client. UDDI registry is one way of handing over this file. Or else this file can be directly given to client.

![[Pasted image 20240814190958.png]]

### **Skeleton in SOAP Web Services**

**A skeleton is a server-side component in a SOAP web service architecture.** It acts as a bridge between the incoming SOAP message and the actual implementation of the web service.

**Role of the Skeleton**

- **Receives incoming SOAP messages:** The skeleton is responsible for accepting SOAP messages from the network.
- **Unmarshals messages:** It parses the incoming XML message into a data structure that can be processed by the application.
- **Dispatches requests:** The skeleton forwards the processed request to the appropriate service implementation.
- **Marshals responses:** Once the service has processed the request, the skeleton converts the response into a SOAP message and sends it back to the client.

### **Stub in SOAP Web Services**

**A stub is a client-side proxy that represents a remote object or service.** In the context of SOAP web services, it's a piece of code on the client side that acts as a local representative of the remote web service.

**Role of the Stub**

- **Local representation:** The stub provides a local interface that mimics the remote service's methods and parameters.
- **Marshalling:** It marshals (converts) data into a format suitable for transmission over the network (usually XML).
- **Network communication:** The stub sends the marshaled data to the remote service using the specified protocol (e.g., HTTP).
- **Unmarshaling:** It unmarshals the response from the remote service and returns it to the client in a usable format.

**How it Works**

When a client invokes a method on the stub, the stub:

1. Packages the method call and parameters into a SOAP message.
2. Sends the SOAP message to the server.
3. Receives the SOAP response from the server.
4. Unpacks the response and returns the result to the client.

**Benefits of Using Stubs**

- **Simplified development:** The client can interact with the remote service as if it were a local object.
- **Improved performance:** By hiding the network communication details, stubs can optimize performance.
- **Error handling:** Stubs can handle exceptions and errors that occur during communication.

**Relationship with Skeleton**

The stub is the client-side counterpart to the skeleton on the server side. They work together to facilitate communication between the client and the web service.
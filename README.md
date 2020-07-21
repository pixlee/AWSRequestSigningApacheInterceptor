# AWS Request Signing Interceptor

An AWS request signing interceptor for arbitrary HttpRequests. (works on java 1.7 and higher)

This enables you to sign requests to any service that leverages SigV4 this means you have a client that can access any AWS Service or APIGW backed service.

## License

This library is licensed under the Apache 2.0 License. 

## Usage
```java
AWS4Signer signer = new AWS4Signer();
    signer.setServiceName(serviceName);
    signer.setRegionName(AWS_REGION);

HttpRequestInterceptor interceptor = new PixleeAWSRequestSigningApacheInterceptor(serviceName, signer, credentialsProvider);

HttpClients.custom()
    .addInterceptorLast(interceptor)
    .build();
```

## Examples

See examples directory for a few valid requests. 

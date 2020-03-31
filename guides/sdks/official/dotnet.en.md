
# Mercado Pago SDK for .Net

This library provides developers with a simple set of bindings to the Mercado Pago API.

### Supported .NET Versions:

This SDK supports .NET version 4.5 or newer.

## Installation

### Using our nuget package

**Using Package Manager**

`PM> Install-Package mercadopago-sdk -Version 1.2.0`

**Using .Net CLI**

`> dotnet add package mercadopago-sdk --version 1.2.0`

**Using Packet CLI**

`> paket add mercadopago-sdk --version 1.2.0`

### Compatibility

Our SDK is compatible with .NET 3.5 or grater. Our development team recomends to use .NET 4.5 or newer versions.

## Quick Start

1. You have to import the Mercado Pago SDK.
```csharp
 using MercadoPago;
```
2. Setup your credentials
-**For Checkout Mercado Pago:**
```csharp
 MercadoPago.SDK.ClientId = "YOUR_CLIENT_ID";
 MercadoPago.SDK.ClientSecret = "YOUR_CLIENT_SECRET";
```
-**For API or custom checkout:**
```csharp
 MercadoPago.SDK.AccessToken = "ENV_ACCESS_TOKEN";
```
3. Using resource objects
You can interact with all the resources available in the public API, to this each resource is represented by classes according to the following diagram:
![SDK resource structure of Mercado Pago](https://user-images.githubusercontent.com/864790/34393059-9acad058-eb2e-11e7-9987-494eaf19d109.png)

**Sample**
```csharp
 using MercadoPago;
 using MercadoPago.Resources;
 using MercadoPago.DataStructures.Payment;
 using MercadoPago.Common;

MercadoPago.SDK.SetAccessToken = "ENV_ACCESS_TOKEN";

 Payment payment = new Payment
 {
     TransactionAmount = (float)100.0,
     Token = "YOUR_CARD_TOKEN"
     Description = "Ergonomic Silk Shirt",
     PaymentMethodId = "visa",
     Installments = 1,
     Payer = new Payer {
         Email = "larue.nienow@hotmail.com"
     }
 };

 payment.Save();

 Console.Out.WriteLine(payment.Status);
```

### Support

Write us at our [support form](/support).
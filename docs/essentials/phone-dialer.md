---
title: "Xamarin.Essentials Phone Dialer"
description: "The PhoneDialer class enables an application to open a web link in the optimized system preferred browser or the external browser."
ms.assetid: E7457942-4D7B-4195-A2FF-417919B9537F
ms.technology: xamarin-crossplatform
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
---
# Xamarin.Essentials Phone Dialer

![Pre-release NuGet](~/media/shared/pre-release.png)

The **PhoneDialer** class enables an application to open a web link in the optimized system preferred browser or the external browser.

## Using Phone Dialer

Add a reference to Xamarin.Essentials in your class:

```csharp
using Xamarin.Essentials;
```

The Phone Dialer functionality works by calling the `Open` method with a phone number to open the dialer with. When `Open` is requested the API will automatically attempt to format the number based on the country code if specified.

```csharp
public class PhoneDialerTest
{
    public async Task PlacePhoneCall(string number)
    {
        try
        {
            PhoneDialer.Open(number);
        }
        catch (ArgumentNullException anEx)
        {
            // Number was null or white space
        }
        catch (FeatureNotSupportedException ex)
        {
            // Phone Dialer is not supported on this device.
        }
        catch (Exception ex)
        {
            // Other error has occurred.
        }
    }
}
```

## API

- [Phone Dialer source code](https://github.com/xamarin/Essentials/tree/master/Essentials/PhoneDialer)
- [Phone Dialer API documentation](xref:Xamarin.Essentials.PhoneDialer)

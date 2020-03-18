---
title: 如何：检测网络可用性和地址更改
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
ms.openlocfilehash: 9e265a97d339da59bb9d0af6ab6757e16af00e06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "70894957"
---
# <a name="how-to-detect-network-availability-and-address-changes"></a><span data-ttu-id="f7ceb-102">如何：检测网络可用性和地址更改</span><span class="sxs-lookup"><span data-stu-id="f7ceb-102">How to: Detect Network Availability and Address Changes</span></span>
<span data-ttu-id="f7ceb-103">此示例演示如何检测接口网络地址中的更改。</span><span class="sxs-lookup"><span data-stu-id="f7ceb-103">This sample shows how to detect changes in the network address of an interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7ceb-104">示例</span><span class="sxs-lookup"><span data-stu-id="f7ceb-104">Example</span></span>  
  
```csharp
using System;  
using System.Net;  
using System.Net.NetworkInformation;  
  
namespace Examples.Net.AddressChanges  
{  
    public class NetworkingExample  
    {  
        public static void Main()  
        {  
            NetworkChange.NetworkAddressChanged += new
             NetworkAddressChangedEventHandler(AddressChangedCallback);  
            Console.WriteLine("Listening for address changes. Press any key to exit.");  
            Console.ReadLine();  
        }  
        static void AddressChangedCallback(object sender, EventArgs e)  
        {  
  
            NetworkInterface[] adapters = NetworkInterface.GetAllNetworkInterfaces();  
            foreach(NetworkInterface n in adapters)  
            {  
                Console.WriteLine("   {0} is {1}", n.Name, n.OperationalStatus);  
            }  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f7ceb-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="f7ceb-105">Compiling the Code</span></span>  
 <span data-ttu-id="f7ceb-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f7ceb-106">This example requires:</span></span>  
  
- <span data-ttu-id="f7ceb-107">引用 System.Net 命名空间  。</span><span class="sxs-lookup"><span data-stu-id="f7ceb-107">References to the **System.Net** namespace.</span></span>

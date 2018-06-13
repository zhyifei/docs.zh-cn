---
title: 如何：检测网络可用性和地址更改
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 9056c8b2ecf18c4a57d356e7c9698984df1558eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396254"
---
# <a name="how-to-detect-network-availability-and-address-changes"></a><span data-ttu-id="b4709-102">如何：检测网络可用性和地址更改</span><span class="sxs-lookup"><span data-stu-id="b4709-102">How to: Detect Network Availability and Address Changes</span></span>
<span data-ttu-id="b4709-103">此示例演示如何检测接口网络地址中的更改。</span><span class="sxs-lookup"><span data-stu-id="b4709-103">This sample shows how to detect changes in the network address of an interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4709-104">示例</span><span class="sxs-lookup"><span data-stu-id="b4709-104">Example</span></span>  
  
```  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="b4709-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="b4709-105">Compiling the Code</span></span>  
 <span data-ttu-id="b4709-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b4709-106">This example requires:</span></span>  
  
-   <span data-ttu-id="b4709-107">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="b4709-107">References to the **System.Net** namespace.</span></span>

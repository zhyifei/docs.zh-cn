---
title: 绑定扩展性
ms.date: 03/30/2017
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
ms.openlocfilehash: af9736a1011c3de6e1add51e8a913745cfd6756d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944087"
---
# <a name="binding-extensibility"></a><span data-ttu-id="13b3e-102">绑定扩展性</span><span class="sxs-lookup"><span data-stu-id="13b3e-102">Binding Extensibility</span></span>

<span data-ttu-id="13b3e-103">本节包含演示自定义绑定 Windows Communication Foundation (WCF) 中的示例。</span><span class="sxs-lookup"><span data-stu-id="13b3e-103">This section contains samples that demonstrate custom binding in Windows Communication Foundation (WCF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13b3e-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="13b3e-104">In This Section</span></span>  
 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="13b3e-105">演示如何实现在 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 之上堆积 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> 或 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> 的绑定。</span><span class="sxs-lookup"><span data-stu-id="13b3e-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 [<span data-ttu-id="13b3e-106">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="13b3e-106">WSStreamedHttpBinding</span></span>](wsstreamedhttpbinding.md)  
 <span data-ttu-id="13b3e-107">演示如何创建一个绑定，该绑定用于在使用 HTTP 传输时支持件流式传送方案。</span><span class="sxs-lookup"><span data-stu-id="13b3e-107">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  

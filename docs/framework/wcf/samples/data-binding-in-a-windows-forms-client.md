---
title: "Windows 窗体客户端中的数据绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 163bd72d9c42680d72c435e8266c75876490a2dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-in-a-windows-forms-client"></a><span data-ttu-id="0eac5-102">Windows 窗体客户端中的数据绑定</span><span class="sxs-lookup"><span data-stu-id="0eac5-102">Data Binding in a Windows Forms Client</span></span>
<span data-ttu-id="0eac5-103">本示例演示如何绑定到由 Windows 窗体应用程序中的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务返回的数据。</span><span class="sxs-lookup"><span data-stu-id="0eac5-103">This sample demonstrates how to bind to data returned by a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in a Windows Forms application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0eac5-104">本文的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="0eac5-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>  
  
 <span data-ttu-id="0eac5-105">本示例演示一个服务，该服务可实现定义“请求-答复”通信模式的协定。</span><span class="sxs-lookup"><span data-stu-id="0eac5-105">This sample demonstrates a service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="0eac5-106">本示例由客户端 Windows 窗体应用程序 (.exe) 和由 Internet 信息服务 (IIS) 承载的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务组成。</span><span class="sxs-lookup"><span data-stu-id="0eac5-106">The sample consists of a client Windows Forms application (.exe) and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="0eac5-107">协定由 `IWeatherService` 接口定义，该接口公开一个名为 `GetWeatherData` 的操作。</span><span class="sxs-lookup"><span data-stu-id="0eac5-107">The contract is defined by the `IWeatherService` interface, which exposes an operation named `GetWeatherData`.</span></span> <span data-ttu-id="0eac5-108">此操作接受一个城市数组并返回一个 `WeatherData` 对象数组，这些对象表示城市的预报高温和预报低温。</span><span class="sxs-lookup"><span data-stu-id="0eac5-108">This operation accepts an array of cities and returns an array of `WeatherData` objects that represent the high and low forecasted temperature for a city.</span></span>  
  
 <span data-ttu-id="0eac5-109">在 Windows 窗体应用程序中的客户端上进行数据绑定。</span><span class="sxs-lookup"><span data-stu-id="0eac5-109">The data binding occurs on the client in the Windows Forms application.</span></span> <span data-ttu-id="0eac5-110">在 Windows 窗体设计器中定义一个 `DataGridView`（它是数据的图形化表示形式）。</span><span class="sxs-lookup"><span data-stu-id="0eac5-110">A `DataGridView` is defined in the Windows Forms designer, which is a graphical representation of the data.</span></span> <span data-ttu-id="0eac5-111">还会创建一个名为 `BindingSource` 的中间媒介。</span><span class="sxs-lookup"><span data-stu-id="0eac5-111">An intermediary named `BindingSource` is also created.</span></span> <span data-ttu-id="0eac5-112">将 `BindingSource` 的数据源设置为由服务返回的数据数组。</span><span class="sxs-lookup"><span data-stu-id="0eac5-112">The data source of `BindingSource` is set to the data array returned by the service.</span></span> <span data-ttu-id="0eac5-113">`BindingSource` 的用途是提供数据与数据视图之间的间接层。</span><span class="sxs-lookup"><span data-stu-id="0eac5-113">The purpose of the `BindingSource` is to provide a layer of indirection between the data and the data view.</span></span> <span data-ttu-id="0eac5-114">与数据的所有交互（如导航、排序、筛选和更新）都是通过调用 `BindingSource` 组件来完成的。</span><span class="sxs-lookup"><span data-stu-id="0eac5-114">All interaction with the data, such as navigating, sorting, filtering, and updating, is accomplished with calls to the `BindingSource` component.</span></span> <span data-ttu-id="0eac5-115">若要完成对 `DataGridView` 的数据绑定，请将 `datasource` 的 `DataGridView` 设置为 `BindingSource` 对象。</span><span class="sxs-lookup"><span data-stu-id="0eac5-115">To accomplish data binding to the `DataGridView`, the `datasource` of the `DataGridView` is then set to the `BindingSource` object.</span></span> <span data-ttu-id="0eac5-116">从 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务返回的所有数据随后会以图形方式向用户进行显示。</span><span class="sxs-lookup"><span data-stu-id="0eac5-116">All of the data returned from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is then displayed graphically to the user.</span></span>  <span data-ttu-id="0eac5-117">每当用户单击按钮时，会在数据绑定的 `DataGridView` 中自动更新返回的数据。</span><span class="sxs-lookup"><span data-stu-id="0eac5-117">Every time the user clicks the button, the returned data is automatically updated in the data-bound `DataGridView`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0eac5-118">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="0eac5-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0eac5-119">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="0eac5-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="0eac5-120">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0eac5-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="0eac5-121">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="0eac5-121">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0eac5-122">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0eac5-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0eac5-123">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0eac5-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0eac5-124">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="0eac5-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0eac5-125">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0eac5-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a><span data-ttu-id="0eac5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0eac5-126">See Also</span></span>

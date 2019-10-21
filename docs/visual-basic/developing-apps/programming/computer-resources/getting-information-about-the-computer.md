---
title: 获取有关计算机的信息 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Info object [Visual Basic], tasks
ms.assetid: 13c145bc-5c85-4fea-a5dd-2ca8681a0252
ms.openlocfilehash: c313f96ec17e2cfb1d94fedebbce5b2f5b8dbc95
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581262"
---
# <a name="getting-information-about-the-computer-visual-basic"></a><span data-ttu-id="a8a78-102">获取有关计算机的信息 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8a78-102">Getting Information about the Computer (Visual Basic)</span></span>

<span data-ttu-id="a8a78-103">`My.Computer.Info` 对象提供了一些属性，可用于获取有关计算机内存、已加载的程序集、名称以及操作系统的信息。</span><span class="sxs-lookup"><span data-stu-id="a8a78-103">The `My.Computer.Info` object provides properties for getting information about the computer's memory, loaded assemblies, name, and operating system.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8a78-104">备注</span><span class="sxs-lookup"><span data-stu-id="a8a78-104">Remarks</span></span>

<span data-ttu-id="a8a78-105">下表列出了通常使用 `My.Computer.Info` 对象完成的任务，并提供了演示如何执行每个任务的主题链接。</span><span class="sxs-lookup"><span data-stu-id="a8a78-105">This table lists tasks commonly accomplished through the `My.Computer.Info` object and points to topics demonstrating how to perform each.</span></span>

|<span data-ttu-id="a8a78-106">功能</span><span class="sxs-lookup"><span data-stu-id="a8a78-106">To</span></span>|<span data-ttu-id="a8a78-107">查看</span><span class="sxs-lookup"><span data-stu-id="a8a78-107">See</span></span>|
|---|---|
|<span data-ttu-id="a8a78-108">确定在安装应用程序的计算机上有多少可用的虚拟地址空间</span><span class="sxs-lookup"><span data-stu-id="a8a78-108">Determine how much virtual address space is available for the computer on which the application is installed</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.TotalVirtualMemory%2A>|
|<span data-ttu-id="a8a78-109">确定正在运行应用程序的计算机的平台类型</span><span class="sxs-lookup"><span data-stu-id="a8a78-109">Determine the platform type of the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSPlatform%2A>|
|<span data-ttu-id="a8a78-110">确定正在运行应用程序的计算机的操作系统</span><span class="sxs-lookup"><span data-stu-id="a8a78-110">Determine the operating system of the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName%2A>|
|<span data-ttu-id="a8a78-111">确定正在运行应用程序的计算机上已安装的服务包</span><span class="sxs-lookup"><span data-stu-id="a8a78-111">Determine what service packs have been installed on the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSVersion%2A>|
|<span data-ttu-id="a8a78-112">确定正在运行应用程序的计算机上已安装的 `UICulture`。</span><span class="sxs-lookup"><span data-stu-id="a8a78-112">Determine the installed `UICulture` on the computer on which the application is running.</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.InstalledUICulture%2A>|

## <a name="see-also"></a><span data-ttu-id="a8a78-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8a78-113">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>

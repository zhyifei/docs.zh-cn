---
title: "在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5"
description: "了解如何在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5。"
author: rlander
ms.author: mairaw
keywords: ".NET Framework, 安装"
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.contentlocale: zh-cn
ms.lasthandoff: 08/05/2017

---

# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="540a2-104">在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="540a2-104">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="540a2-105">必须安装 .NET Framework 3.5，才能在 Windows 10、Windows 8.1 和 Windows 8 上运行应用。</span><span class="sxs-lookup"><span data-stu-id="540a2-105">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="540a2-106">对于旧版 Windows，也可以按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="540a2-106">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="540a2-107">按需安装.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="540a2-107">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="540a2-108">如果尝试运行的应用要求安装 .NET Framework 3.5，则会看到以下配置对话框。</span><span class="sxs-lookup"><span data-stu-id="540a2-108">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="540a2-109">选择“安装此功能”，启用 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="540a2-109">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="540a2-110">此选项需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="540a2-110">This option requires an Internet connection.</span></span>

![.NET Framework 安装对话框](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="540a2-112">在控制面板中启用 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="540a2-112">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="540a2-113">可以通过 Windows 控制面板启用 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="540a2-113">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="540a2-114">此选项需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="540a2-114">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="540a2-115">按键盘上的 Windows 键 ![Windows 徽标](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg)，键入“Windows 功能”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="540a2-115">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="540a2-116">随即显示“打开或关闭 Windows 功能”对话框。</span><span class="sxs-lookup"><span data-stu-id="540a2-116">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="540a2-117">如果弹出提示，选择“.NET Framework 3.5 (包括 .NET 2.0 和 3.0)” 复选框，选择“确定”，然后重启计算机。</span><span class="sxs-lookup"><span data-stu-id="540a2-117">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![使用控制面板安装 .NET](./media/dotnet-control-panel.png)

   <span data-ttu-id="540a2-119">无需选择“Windows Communication Foundation (WCF) HTTP 激活”和“Windows Communication Foundation (WCF) 非 HTTP 激活”的子项，除非是需要使用此功能的开发者或服务器管理员。</span><span class="sxs-lookup"><span data-stu-id="540a2-119">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>


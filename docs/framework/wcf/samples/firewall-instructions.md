---
title: "防火墙说明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 38d1f0f6bf9245048f21bbe1cb0aa6a0b8d768dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="firewall-instructions"></a><span data-ttu-id="7a2ec-102">防火墙说明</span><span class="sxs-lookup"><span data-stu-id="7a2ec-102">Firewall Instructions</span></span>
<span data-ttu-id="7a2ec-103">必须在防火墙中启用若干端口或程序，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 示例才能运行。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-103">You must enable several ports or programs in the firewall so that the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples can function.</span></span> <span data-ttu-id="7a2ec-104">其中许多示例使用范围 8000-8003 中的端口和端口 9000 进行通信。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="7a2ec-105">防火墙默认情况下会打开，阻止对这些端口进行访问。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="7a2ec-106">若要针对这些示例启用防火墙，请完成以下过程之一，具体情况取决于您的要求和安全环境：</span><span class="sxs-lookup"><span data-stu-id="7a2ec-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>  
  
-   <span data-ttu-id="7a2ec-107">选项 1：在运行时以交互方式启用示例。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="7a2ec-108">不预先更改防火墙配置，并继续开始生成和运行示例的过程。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="7a2ec-109">当运行示例时， **Windows 安全警报**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="7a2ec-110">然后，可以通过交互方式将所讨论的示例程序添加到取消阻止列表。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="7a2ec-111">对于此过程，您可能必须随后重新启动示例。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-111">With this procedure, you may have to then restart the sample.</span></span>  
  
-   <span data-ttu-id="7a2ec-112">选项 2：预先启用示例程序。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="7a2ec-113">启动**Windows 防火墙控制面板**小程序，并启用示例程序计划运行。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="7a2ec-114">您必须首先生成这些程序，以生成它们的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="7a2ec-115">可以在以下过程中找到更详细的说明。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-115">You can find more detailed instructions in the following procedure.</span></span>  
  
-   <span data-ttu-id="7a2ec-116">选项 3：预先启用端口范围。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="7a2ec-117">启动**Windows 防火墙****控制面板**小程序并启用端口 80、 443、 8000-8003 和 9000，所使用的这些示例。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-117">Start the **Windows Firewall** **Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="7a2ec-118">可以在以下过程中找到更详细的说明。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="7a2ec-119">相对于其他选项而言，此选项的安全性较差，因为它允许任何程序（而不仅仅是示例）使用这些端口。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>  
  
 <span data-ttu-id="7a2ec-120">如果不确定要使用哪个过程，请选择第一个选项。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="7a2ec-121">如果运行其他供应商提供的防火墙，您可能需要进行类似的更改。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7a2ec-122">更改防火墙配置会对安全产生影响。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="7a2ec-123">建议您记录所做的更改，并在使用完示例后移除这些更改。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>  
  
### <a name="to-enable-samples-programs-in-advance"></a><span data-ttu-id="7a2ec-124">预先启用示例程序</span><span class="sxs-lookup"><span data-stu-id="7a2ec-124">To enable samples programs in advance</span></span>  
  
1.  <span data-ttu-id="7a2ec-125">生成示例。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-125">Build the sample.</span></span>  
  
2.  <span data-ttu-id="7a2ec-126">单击**启动**，单击**运行**，和类型`firewall.cpl`。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-126">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="7a2ec-127">这将打开**Windows 防火墙控制面板**小程序。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-127">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a2ec-128">必须具有更改防火墙设置的权限，才能运行需要能够通过 Windows 防火墙进行通信的示例。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="7a2ec-129">如果某些防火墙设置不可用，并且您的计算机连接到域，则系统管理员可以通过组策略控制这些设置。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>  
  
3.  <span data-ttu-id="7a2ec-130">完成以下特定于操作系统的步骤之一，允许程序通过 Windows 防火墙：</span><span class="sxs-lookup"><span data-stu-id="7a2ec-130">Complete one of the following operating specific steps to allow a program through the Windows Firewall:</span></span>  
  
    -   <span data-ttu-id="7a2ec-131">在 Windows 7 或 Windows Server 2008 r2 上，单击**允许程序或功能通过 Windows 防火墙**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-131">On Windows 7 or Windows Server 2008 r2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="7a2ec-132">单击**更改设置**，允许**另一个程序...**.</span><span class="sxs-lookup"><span data-stu-id="7a2ec-132">Click **Change Settings**, Allow **Another Program…**.</span></span>  
  
    -   <span data-ttu-id="7a2ec-133">上[!INCLUDE[wv](../../../../includes/wv-md.md)]或[!INCLUDE[lserver](../../../../includes/lserver-md.md)]，单击**允许程序通过 Windows 防火墙**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-133">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], click **Allow a program through Windows Firewall**.</span></span>  
  
4.  <span data-ttu-id="7a2ec-134">上**异常**选项卡上，单击**添加程序**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-134">On the **Exceptions** tab, click **Add Program**.</span></span>  
  
5.  <span data-ttu-id="7a2ec-135">单击**浏览**按钮，然后选择你打算运行示例的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>  
  
6.  <span data-ttu-id="7a2ec-136">直到已添加你打算运行的所有示例的可执行文件，请重复步骤 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>  
  
7.  <span data-ttu-id="7a2ec-137">单击**确定**关闭防火墙小程序。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-137">Click **OK** to close the firewall applet.</span></span>  
  
### <a name="to-enable-a-port-range-in-advance"></a><span data-ttu-id="7a2ec-138">预先启用端口范围</span><span class="sxs-lookup"><span data-stu-id="7a2ec-138">To enable a port range in advance</span></span>  
  
1.  <span data-ttu-id="7a2ec-139">单击**启动**，单击**运行**，和类型`firewall.cpl`。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-139">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="7a2ec-140">这将打开**Windows 防火墙控制面板**小程序。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-140">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
2.  <span data-ttu-id="7a2ec-141">在 Windows 7 或 Windows Server 2008 R2 上，按以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="7a2ec-142">单击**高级设置**Windows 防火墙窗口左列中。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>  
  
    2.  <span data-ttu-id="7a2ec-143">单击**入站规则**左侧列中。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-143">Click **Inbound Rules** in the left column.</span></span>  
  
    3.  <span data-ttu-id="7a2ec-144">单击**新规则**右侧列中。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-144">Click **New Rules** in the right column.</span></span>  
  
    4.  <span data-ttu-id="7a2ec-145">选择**端口**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-145">Select **Port** and click **next**.</span></span>  
  
    5.  <span data-ttu-id="7a2ec-146">选择**TCP**并输入`8000, 8001, 8002, 8003, 9000, 80, 443`中**特定本地端口**字段。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>  
  
    6.  <span data-ttu-id="7a2ec-147">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-147">Click **Next**.</span></span>  
  
    7.  <span data-ttu-id="7a2ec-148">选择**允许连接**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-148">Select **Allow the connection**, and click **Next** .</span></span>  
  
    8.  <span data-ttu-id="7a2ec-149">选择**域**和**私有**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-149">Select **Domain** and **Private**, and click **Next**.</span></span>  
  
    9. <span data-ttu-id="7a2ec-150">此规则命名为`WCF-WF 4.0 Samples`，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>  
  
    10. <span data-ttu-id="7a2ec-151">单击**出站规则**并重复执行步骤 c 到 h。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-151">Click **Outbound Rules** and repeat steps c to h.</span></span>  
  
3.  <span data-ttu-id="7a2ec-152">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 或 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上，按以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-152">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], follow these steps.</span></span>  
  
    1.  <span data-ttu-id="7a2ec-153">单击**允许程序通过 Windows 防火墙**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-153">Click **Allow a program through Windows Firewall**.</span></span>  
  
    2.  <span data-ttu-id="7a2ec-154">上**异常**选项卡上，单击**添加端口**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-154">On the **Exceptions** tab, click **Add Port**.</span></span>  
  
    3.  <span data-ttu-id="7a2ec-155">输入的名称，输入 8000 作为端口号，然后选择**TCP**选项。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>  
  
    4.  <span data-ttu-id="7a2ec-156">单击**更改作用域**按钮，选择**我网络**（子网） 的唯一选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>  
  
    5.  <span data-ttu-id="7a2ec-157">为端口 8001、8002、8003、9000、80 和 443 重复步骤 b 到 d。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>  
  
4.  <span data-ttu-id="7a2ec-158">单击**确定**关闭防火墙小程序。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-158">Click **OK** to close the firewall applet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a2ec-159">使用完示例后，请移除任何防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="7a2ec-160">为此，请打开**Windows 防火墙控制面板**小程序并删除任何程序或端口上一个过程中添加的项。</span><span class="sxs-lookup"><span data-stu-id="7a2ec-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>

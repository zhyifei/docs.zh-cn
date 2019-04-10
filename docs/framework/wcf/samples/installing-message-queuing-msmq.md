---
title: 安装“消息队列 (MSMQ)”
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 64736f8f0a34a53658dd2838738a3d36b3891d2d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305086"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="236a7-102">安装“消息队列 (MSMQ)”</span><span class="sxs-lookup"><span data-stu-id="236a7-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="236a7-103">以下过程介绍如何安装“消息队列 4.0”和“消息队列 3.0”。</span><span class="sxs-lookup"><span data-stu-id="236a7-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="236a7-104">消息队列 4.0 在 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 和 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 中不可用。</span><span class="sxs-lookup"><span data-stu-id="236a7-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="236a7-105">在 Windows Server 2008 or Windows Server 2008 R2 上安装消息队列 4.0</span><span class="sxs-lookup"><span data-stu-id="236a7-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="236a7-106">在服务器管理器中，单击**功能**。</span><span class="sxs-lookup"><span data-stu-id="236a7-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="236a7-107">在右侧窗格中下,**功能摘要**，单击**添加功能**。</span><span class="sxs-lookup"><span data-stu-id="236a7-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="236a7-108">在生成的窗口中，展开**消息队列**。</span><span class="sxs-lookup"><span data-stu-id="236a7-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="236a7-109">展开**消息队列服务**。</span><span class="sxs-lookup"><span data-stu-id="236a7-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="236a7-110">单击**目录服务集成**（用于计算机加入到域的），然后单击**HTTP 支持**。</span><span class="sxs-lookup"><span data-stu-id="236a7-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="236a7-111">单击**下一步**，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="236a7-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="236a7-112">在 Windows 7 或 Windows Vista 上安装消息队列 4.0</span><span class="sxs-lookup"><span data-stu-id="236a7-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="236a7-113">打开“控制面板” 。</span><span class="sxs-lookup"><span data-stu-id="236a7-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="236a7-114">单击**程序**，然后在**程序和功能**，单击**打开或关闭 Windows 功能**。</span><span class="sxs-lookup"><span data-stu-id="236a7-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="236a7-115">展开“Microsoft Message Queue (MSMQ) 服务器”，展开“Microsoft Message Queue (MSMQ) 服务器核心”，然后选中对应于以下要安装的“消息队列”功能的复选框：</span><span class="sxs-lookup"><span data-stu-id="236a7-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    -   <span data-ttu-id="236a7-116">MSMQ Active Directory 域服务集成（用于加入域的计算机）。</span><span class="sxs-lookup"><span data-stu-id="236a7-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    -   <span data-ttu-id="236a7-117">MSMQ HTTP 支持。</span><span class="sxs-lookup"><span data-stu-id="236a7-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="236a7-118">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="236a7-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="236a7-119">如果系统提示您重新启动计算机时，请单击**确定**以完成安装。</span><span class="sxs-lookup"><span data-stu-id="236a7-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="236a7-120">在 Windows XP 和 Windows Server 2003 上安装消息队列 3.0</span><span class="sxs-lookup"><span data-stu-id="236a7-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="236a7-121">打开“控制面板” 。</span><span class="sxs-lookup"><span data-stu-id="236a7-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="236a7-122">单击**添加或删除程序**，然后单击**添加 Windows 组件**。</span><span class="sxs-lookup"><span data-stu-id="236a7-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="236a7-123">选择消息队列，然后单击**详细信息**。</span><span class="sxs-lookup"><span data-stu-id="236a7-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="236a7-124">如果运行的是 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]，请选择“应用程序服务器”来访问消息队列。</span><span class="sxs-lookup"><span data-stu-id="236a7-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="236a7-125">确保在详细信息页上已选中“MSMQ HTTP 支持”选项。</span><span class="sxs-lookup"><span data-stu-id="236a7-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="236a7-126">单击**确定**以退出详细信息页上，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="236a7-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="236a7-127">完成安装。</span><span class="sxs-lookup"><span data-stu-id="236a7-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="236a7-128">如果系统提示您重新启动计算机时，请单击**确定**以完成安装。</span><span class="sxs-lookup"><span data-stu-id="236a7-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="236a7-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="236a7-129">See also</span></span>

- [<span data-ttu-id="236a7-130">设置说明</span><span class="sxs-lookup"><span data-stu-id="236a7-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)

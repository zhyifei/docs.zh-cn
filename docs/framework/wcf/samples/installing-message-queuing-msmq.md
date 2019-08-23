---
title: 安装“消息队列 (MSMQ)”
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 42e66029f8538877ded424f72cb6c829444d1ee0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935982"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="d0bd5-102">安装“消息队列 (MSMQ)”</span><span class="sxs-lookup"><span data-stu-id="d0bd5-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="d0bd5-103">以下过程介绍如何安装“消息队列 4.0”和“消息队列 3.0”。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0bd5-104">消息队列 4.0 在 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 和 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 中不可用。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="d0bd5-105">在 Windows Server 2008 or Windows Server 2008 R2 上安装消息队列 4.0</span><span class="sxs-lookup"><span data-stu-id="d0bd5-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="d0bd5-106">在服务器管理器中, 单击 "**功能**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="d0bd5-107">在右侧窗格中的 "**功能摘要**" 下, 单击 "**添加功能**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="d0bd5-108">在生成的窗口中, 展开 "**消息队列**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="d0bd5-109">展开 "**消息队列服务**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="d0bd5-110">单击 "**目录服务集成**" (对于加入域的计算机), 然后单击 " **HTTP 支持**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="d0bd5-111">单击 "**下一步**", 然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="d0bd5-112">在 Windows 7 或 Windows Vista 上安装消息队列 4.0</span><span class="sxs-lookup"><span data-stu-id="d0bd5-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="d0bd5-113">打开“控制面板”。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="d0bd5-114">单击 "**程序**", 然后在 "**程序和功能**" 下, 单击 "**打开和关闭 Windows 功能**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="d0bd5-115">展开“Microsoft Message Queue (MSMQ) 服务器”，展开“Microsoft Message Queue (MSMQ) 服务器核心”，然后选中对应于以下要安装的“消息队列”功能的复选框：</span><span class="sxs-lookup"><span data-stu-id="d0bd5-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="d0bd5-116">MSMQ Active Directory 域服务集成（用于加入域的计算机）。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="d0bd5-117">MSMQ HTTP 支持。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="d0bd5-118">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="d0bd5-119">如果系统提示您重新启动计算机, 请单击 **"确定"** 以完成安装。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="d0bd5-120">在 Windows XP 和 Windows Server 2003 上安装消息队列 3.0</span><span class="sxs-lookup"><span data-stu-id="d0bd5-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="d0bd5-121">打开“控制面板”。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="d0bd5-122">单击 "**添加删除程序**", 然后单击 "**添加 Windows 组件**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="d0bd5-123">选择 "消息队列", 然后单击 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0bd5-124">如果运行的是 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]，请选择“应用程序服务器”来访问消息队列。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="d0bd5-125">确保在详细信息页上已选中“MSMQ HTTP 支持”选项。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="d0bd5-126">单击 **"确定"** 退出详细信息页, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="d0bd5-127">完成安装。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="d0bd5-128">如果系统提示您重新启动计算机, 请单击 **"确定"** 以完成安装。</span><span class="sxs-lookup"><span data-stu-id="d0bd5-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0bd5-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0bd5-129">See also</span></span>

- [<span data-ttu-id="d0bd5-130">设置说明</span><span class="sxs-lookup"><span data-stu-id="d0bd5-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)

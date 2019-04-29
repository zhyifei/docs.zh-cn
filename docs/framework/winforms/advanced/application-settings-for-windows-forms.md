---
title: Windows 窗体的应用程序设置
ms.date: 04/07/2017
f1_keywords:
- ClientApplicationSettings
helpviewer_keywords:
- application settings [Windows Forms]
- Windows Forms, application settings
ms.assetid: 64090a34-8556-4904-8ea0-20efe9f8c886
ms.openlocfilehash: 0cac4433ec9fe54721752c63d2b3b37f9d874c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779140"
---
# <a name="application-settings-for-windows-forms"></a><span data-ttu-id="57adc-102">Windows 窗体的应用程序设置</span><span class="sxs-lookup"><span data-stu-id="57adc-102">Application Settings for Windows Forms</span></span>
<span data-ttu-id="57adc-103">借助 Windows 窗体的应用程序设置功能，可轻松地在客户端创建、存储和维护自定义应用程序和用户首选项。</span><span class="sxs-lookup"><span data-stu-id="57adc-103">The Applications Settings feature of Windows Forms makes it easy to create, store, and maintain custom application and user preferences on the client.</span></span> <span data-ttu-id="57adc-104">借助应用程序设置，可存储应用程序数据（如数据库连接字符串）以及用户特定的数据（如工具栏位置和最近使用的列表）。</span><span class="sxs-lookup"><span data-stu-id="57adc-104">With Application Settings, you can store not only application data such as database connection strings, but also user-specific data, such as toolbar positions and most-recently used lists.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57adc-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="57adc-105">In This Section</span></span>  
 [<span data-ttu-id="57adc-106">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="57adc-106">Application Settings Overview</span></span>](~/docs/framework/winforms/advanced/application-settings-overview.md)  
 <span data-ttu-id="57adc-107">讨论如何代表你的应用程序和你的用户创建和存储设置数据。</span><span class="sxs-lookup"><span data-stu-id="57adc-107">Discusses how to create and store settings data on behalf of your application and your users.</span></span>  
  
 [<span data-ttu-id="57adc-108">应用程序设置体系结构</span><span class="sxs-lookup"><span data-stu-id="57adc-108">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)  
 <span data-ttu-id="57adc-109">介绍应用程序设置功能的工作原理，并探讨了体系结构（如分组设置和设置键）的高级功能。</span><span class="sxs-lookup"><span data-stu-id="57adc-109">Describes how the Application Settings feature works, and explores advanced features of the architecture such as grouped settings and settings keys.</span></span>  
  
 [<span data-ttu-id="57adc-110">应用程序设置特性</span><span class="sxs-lookup"><span data-stu-id="57adc-110">Application Settings Attributes</span></span>](~/docs/framework/winforms/advanced/application-settings-attributes.md)  
 <span data-ttu-id="57adc-111">列出并介绍了可应用于应用程序设置包装类或其设置属性的属性。</span><span class="sxs-lookup"><span data-stu-id="57adc-111">Lists and describes the attributes that can be applied to an application settings wrapper class or its settings properties.</span></span>  
  
 [<span data-ttu-id="57adc-112">Application Settings for Custom Controls</span><span class="sxs-lookup"><span data-stu-id="57adc-112">Application Settings for Custom Controls</span></span>](~/docs/framework/winforms/advanced/application-settings-for-custom-controls.md)  
 <span data-ttu-id="57adc-113">讨论必须执行什么操作以使自定义控件在第三方应用程序中承载时可以保存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="57adc-113">Discusses what must be done to give your custom controls the ability to persist application settings when hosted in third-party applications.</span></span>  
  
 [<span data-ttu-id="57adc-114">如何：创建应用程序设置</span><span class="sxs-lookup"><span data-stu-id="57adc-114">How to: Create Application Settings</span></span>](~/docs/framework/winforms/advanced/how-to-create-application-settings.md)  
 <span data-ttu-id="57adc-115">演示如何创建在应用程序会话之间保存的新应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="57adc-115">Demonstrates creating new application settings that are persisted between application sessions.</span></span>  
  
 [<span data-ttu-id="57adc-116">如何：验证应用程序设置</span><span class="sxs-lookup"><span data-stu-id="57adc-116">How to: Validate Application Settings</span></span>](~/docs/framework/winforms/advanced/how-to-validate-application-settings.md)  
 <span data-ttu-id="57adc-117">演示如何在保存前验证应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="57adc-117">Demonstrates validating application settings before they are persisted.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="57adc-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="57adc-118">Related topics</span></span>

<span data-ttu-id="57adc-119">[Windows 窗体配置节](../../configure-apps/file-schema/winforms/index.md)  </span><span class="sxs-lookup"><span data-stu-id="57adc-119">[Windows Forms Configuration Section](../../configure-apps/file-schema/winforms/index.md)  </span></span>  
<span data-ttu-id="57adc-120">文档支持在 Windows 窗体应用程序从.NET Framework 4.7 开始启用高 DPI 的设置。</span><span class="sxs-lookup"><span data-stu-id="57adc-120">Documents the settings to enable High DPI support in Windows Forms Application starting with the .NET Framework 4.7.</span></span>

## <a name="see-also"></a><span data-ttu-id="57adc-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="57adc-121">See also</span></span>

- [<span data-ttu-id="57adc-122">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="57adc-122">Windows Forms</span></span>](../index.md)

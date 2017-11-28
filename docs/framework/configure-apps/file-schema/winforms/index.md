---
title: "Windows 窗体配置节"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b83f00f82de727812c5737915a6dc35ec98e4734
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="7ab3a-102">Windows 窗体配置节</span><span class="sxs-lookup"><span data-stu-id="7ab3a-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="7ab3a-103">Windows 窗体配置设置允许 Windows 窗体应用存储和检索有关自定义应用程序设置的信息，如多显示器支持、高 DPI 支持和其他预定义配置设置。</span><span class="sxs-lookup"><span data-stu-id="7ab3a-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="7ab3a-104">Windows 窗体应用程序配置设置存储在应用程序配置文件的 `System.Windows.Forms.ApplicationConfigurationSection` 元素中。</span><span class="sxs-lookup"><span data-stu-id="7ab3a-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ab3a-105">语法</span><span class="sxs-lookup"><span data-stu-id="7ab3a-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7ab3a-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7ab3a-106">Attributes and elements</span></span>

<span data-ttu-id="7ab3a-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7ab3a-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7ab3a-108">特性</span><span class="sxs-lookup"><span data-stu-id="7ab3a-108">Attributes</span></span>

<span data-ttu-id="7ab3a-109">无。</span><span class="sxs-lookup"><span data-stu-id="7ab3a-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7ab3a-110">子元素</span><span class="sxs-lookup"><span data-stu-id="7ab3a-110">Child elements</span></span>

<span data-ttu-id="7ab3a-111">元素</span><span class="sxs-lookup"><span data-stu-id="7ab3a-111">Element</span></span>  |<span data-ttu-id="7ab3a-112">描述</span><span class="sxs-lookup"><span data-stu-id="7ab3a-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="7ab3a-113">添加具有指定值的配置设置键</span><span class="sxs-lookup"><span data-stu-id="7ab3a-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="7ab3a-114">父元素</span><span class="sxs-lookup"><span data-stu-id="7ab3a-114">Parent elements</span></span>

<span data-ttu-id="7ab3a-115">元素</span><span class="sxs-lookup"><span data-stu-id="7ab3a-115">Element</span></span>  |<span data-ttu-id="7ab3a-116">描述</span><span class="sxs-lookup"><span data-stu-id="7ab3a-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="7ab3a-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7ab3a-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="7ab3a-118">公共语言运行时和 .Windows 窗体应用程序所使用的每个配置文件中的根元素</span><span class="sxs-lookup"><span data-stu-id="7ab3a-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="7ab3a-119">备注</span><span class="sxs-lookup"><span data-stu-id="7ab3a-119">Remarks</span></span>

<span data-ttu-id="7ab3a-120">从 .NET Framework 4.7 开始，`<System.Windows.Forms.ApplicationConfigurationSection>` 元素允许配置 Windows 窗体应用程序，以利用最新版本的 .NET Framework 中添加的功能。</span><span class="sxs-lookup"><span data-stu-id="7ab3a-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="7ab3a-121">`<System.Windows.Forms.ApplicationConfigurationSection>` 元素可以包含一个或多个子 [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) 元素，每个元素都定义了一个特定的配置设置。</span><span class="sxs-lookup"><span data-stu-id="7ab3a-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ab3a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ab3a-122">See also</span></span>

<span data-ttu-id="7ab3a-123">[配置文件架构](../index.md) </span><span class="sxs-lookup"><span data-stu-id="7ab3a-123">[Configuration File Schema](../index.md) </span></span>  
[<span data-ttu-id="7ab3a-124">Windows 窗体中的高 DPI 支持</span><span class="sxs-lookup"><span data-stu-id="7ab3a-124">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)

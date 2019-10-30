---
title: Windows 窗体配置节
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 4a54df0b6301f1aae14d5561c91c6792cb0a1620
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109815"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="bd027-102">Windows 窗体配置节</span><span class="sxs-lookup"><span data-stu-id="bd027-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="bd027-103">Windows 窗体配置设置允许 Windows 窗体应用存储和检索有关自定义应用程序设置的信息，如多显示器支持、高 DPI 支持和其他预定义配置设置。</span><span class="sxs-lookup"><span data-stu-id="bd027-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="bd027-104">Windows 窗体应用程序配置设置存储在应用程序配置文件的 `System.Windows.Forms.ApplicationConfigurationSection` 元素中。</span><span class="sxs-lookup"><span data-stu-id="bd027-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd027-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd027-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bd027-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bd027-106">Attributes and elements</span></span>

<span data-ttu-id="bd027-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bd027-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bd027-108">特性</span><span class="sxs-lookup"><span data-stu-id="bd027-108">Attributes</span></span>

<span data-ttu-id="bd027-109">无。</span><span class="sxs-lookup"><span data-stu-id="bd027-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bd027-110">子元素</span><span class="sxs-lookup"><span data-stu-id="bd027-110">Child elements</span></span>

<span data-ttu-id="bd027-111">元素</span><span class="sxs-lookup"><span data-stu-id="bd027-111">Element</span></span>  |<span data-ttu-id="bd027-112">描述</span><span class="sxs-lookup"><span data-stu-id="bd027-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="bd027-113">添加具有指定值的配置设置键</span><span class="sxs-lookup"><span data-stu-id="bd027-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="bd027-114">父元素</span><span class="sxs-lookup"><span data-stu-id="bd027-114">Parent elements</span></span>

<span data-ttu-id="bd027-115">元素</span><span class="sxs-lookup"><span data-stu-id="bd027-115">Element</span></span>  |<span data-ttu-id="bd027-116">描述</span><span class="sxs-lookup"><span data-stu-id="bd027-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="bd027-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bd027-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="bd027-118">公共语言运行时和 .Windows 窗体应用程序所使用的每个配置文件中的根元素</span><span class="sxs-lookup"><span data-stu-id="bd027-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="bd027-119">备注</span><span class="sxs-lookup"><span data-stu-id="bd027-119">Remarks</span></span>

<span data-ttu-id="bd027-120">从 .NET Framework 4.7 开始，`<System.Windows.Forms.ApplicationConfigurationSection>` 元素允许配置 Windows 窗体应用程序，以利用最新版本的 .NET Framework 中添加的功能。</span><span class="sxs-lookup"><span data-stu-id="bd027-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="bd027-121">`<System.Windows.Forms.ApplicationConfigurationSection>` 元素可以包含一个或多个子 [`<add>`](windows-forms-add-configuration-element.md) 元素，每个元素都定义了一个特定的配置设置。</span><span class="sxs-lookup"><span data-stu-id="bd027-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd027-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd027-122">See also</span></span>

- [<span data-ttu-id="bd027-123">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="bd027-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bd027-124">Windows 窗体中的高 DPI 支持</span><span class="sxs-lookup"><span data-stu-id="bd027-124">High DPI Support in Windows Forms</span></span>](../../../winforms/high-dpi-support-in-windows-forms.md)

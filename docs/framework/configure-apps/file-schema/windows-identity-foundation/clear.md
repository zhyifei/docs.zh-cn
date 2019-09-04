---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: e96349c72fc4a952e3dc7efeea5f69ebaa1fd0ad
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252045"
---
# <a name="clear"></a><span data-ttu-id="02f43-101">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="02f43-101">\<clear></span></span>
<span data-ttu-id="02f43-102">清除当前标记处理程序集合中的所有安全标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="02f43-102">Clears all security token handlers from the current token handler collection.</span></span>  
  
<span data-ttu-id="02f43-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02f43-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02f43-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="02f43-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="02f43-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="02f43-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="02f43-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="02f43-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="02f43-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<清除 >**</span><span class="sxs-lookup"><span data-stu-id="02f43-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02f43-108">语法</span><span class="sxs-lookup"><span data-stu-id="02f43-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <clear>  
      </clear>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02f43-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02f43-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02f43-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="02f43-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02f43-111">特性</span><span class="sxs-lookup"><span data-stu-id="02f43-111">Attributes</span></span>  
 <span data-ttu-id="02f43-112">无</span><span class="sxs-lookup"><span data-stu-id="02f43-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02f43-113">子元素</span><span class="sxs-lookup"><span data-stu-id="02f43-113">Child Elements</span></span>  
 <span data-ttu-id="02f43-114">无</span><span class="sxs-lookup"><span data-stu-id="02f43-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02f43-115">父元素</span><span class="sxs-lookup"><span data-stu-id="02f43-115">Parent Elements</span></span>  
  
|<span data-ttu-id="02f43-116">元素</span><span class="sxs-lookup"><span data-stu-id="02f43-116">Element</span></span>|<span data-ttu-id="02f43-117">描述</span><span class="sxs-lookup"><span data-stu-id="02f43-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02f43-118">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="02f43-118">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="02f43-119">指定注册到终结点的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="02f43-119">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|

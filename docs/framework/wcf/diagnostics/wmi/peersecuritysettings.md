---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 02cd483f2f7ec5e599b286b672d051a0e8d57940
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="ad6ef-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ad6ef-102">PeerSecuritySettings</span></span>
<span data-ttu-id="ad6ef-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ad6ef-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad6ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad6ef-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ad6ef-105">方法</span><span class="sxs-lookup"><span data-stu-id="ad6ef-105">Methods</span></span>  
 <span data-ttu-id="ad6ef-106">PeerSecuritySettings 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ad6ef-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ad6ef-107">属性</span><span class="sxs-lookup"><span data-stu-id="ad6ef-107">Properties</span></span>  
 <span data-ttu-id="ad6ef-108">PeerSecuritySettings 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="ad6ef-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="ad6ef-109">模式</span><span class="sxs-lookup"><span data-stu-id="ad6ef-109">Mode</span></span>  
 <span data-ttu-id="ad6ef-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ad6ef-110">Data type: string</span></span>  
  
 <span data-ttu-id="ad6ef-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad6ef-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad6ef-112">配置有绑定的终结点是否使用消息级别和传输级别安全。</span><span class="sxs-lookup"><span data-stu-id="ad6ef-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="ad6ef-113">传输</span><span class="sxs-lookup"><span data-stu-id="ad6ef-113">Transport</span></span>  
 <span data-ttu-id="ad6ef-114">数据类型：PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ad6ef-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="ad6ef-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad6ef-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad6ef-116">传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="ad6ef-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad6ef-117">要求</span><span class="sxs-lookup"><span data-stu-id="ad6ef-117">Requirements</span></span>  
  
|<span data-ttu-id="ad6ef-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ad6ef-118">MOF</span></span>|<span data-ttu-id="ad6ef-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ad6ef-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad6ef-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="ad6ef-120">Namespace</span></span>|<span data-ttu-id="ad6ef-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ad6ef-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad6ef-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad6ef-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>

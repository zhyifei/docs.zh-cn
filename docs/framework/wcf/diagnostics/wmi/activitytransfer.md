---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662812"
---
# <a name="activitytransfer"></a><span data-ttu-id="79059-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="79059-102">ActivityTransfer</span></span>
<span data-ttu-id="79059-103">活动传输事件</span><span class="sxs-lookup"><span data-stu-id="79059-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79059-104">语法</span><span class="sxs-lookup"><span data-stu-id="79059-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="79059-105">方法</span><span class="sxs-lookup"><span data-stu-id="79059-105">Methods</span></span>  
 <span data-ttu-id="79059-106">ActivityTransfer 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="79059-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="79059-107">属性</span><span class="sxs-lookup"><span data-stu-id="79059-107">Properties</span></span>  
 <span data-ttu-id="79059-108">ActivityTransfer 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="79059-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="79059-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="79059-109">ActivityID</span></span>  
  
- <span data-ttu-id="79059-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="79059-110">Data type: object</span></span>  
    <span data-ttu-id="79059-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="79059-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="79059-112">活动 ID</span><span class="sxs-lookup"><span data-stu-id="79059-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="79059-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="79059-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="79059-114">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="79059-114">Data type: object</span></span>  
    <span data-ttu-id="79059-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="79059-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="79059-116">相关活动 ID</span><span class="sxs-lookup"><span data-stu-id="79059-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79059-117">要求</span><span class="sxs-lookup"><span data-stu-id="79059-117">Requirements</span></span>  
  
|<span data-ttu-id="79059-118">MOF</span><span class="sxs-lookup"><span data-stu-id="79059-118">MOF</span></span>|<span data-ttu-id="79059-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="79059-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="79059-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="79059-120">Namespace</span></span>|<span data-ttu-id="79059-121">已在 root\ServiceModel 中定义。</span><span class="sxs-lookup"><span data-stu-id="79059-121">Defined in root\ServiceModel.</span></span>|

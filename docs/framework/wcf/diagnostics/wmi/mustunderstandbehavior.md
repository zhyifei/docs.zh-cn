---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 7e6a96c217b038e870b4e865315766afa3b3c757
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165450"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="c9902-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="c9902-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="c9902-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="c9902-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9902-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9902-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c9902-105">方法</span><span class="sxs-lookup"><span data-stu-id="c9902-105">Methods</span></span>  
 <span data-ttu-id="c9902-106">MustUnderstandBehavior 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="c9902-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c9902-107">属性</span><span class="sxs-lookup"><span data-stu-id="c9902-107">Properties</span></span>  
 <span data-ttu-id="c9902-108">MustUnderstandBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="c9902-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="c9902-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="c9902-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="c9902-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="c9902-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="c9902-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c9902-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9902-112">如果为 `true`，则所有具有 `MustUnderstand` 属性的未处理 SOAP 标头将导致引发异常的行为。</span><span class="sxs-lookup"><span data-stu-id="c9902-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9902-113">要求</span><span class="sxs-lookup"><span data-stu-id="c9902-113">Requirements</span></span>  
  
|<span data-ttu-id="c9902-114">MOF</span><span class="sxs-lookup"><span data-stu-id="c9902-114">MOF</span></span>|<span data-ttu-id="c9902-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="c9902-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c9902-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="c9902-116">Namespace</span></span>|<span data-ttu-id="c9902-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="c9902-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9902-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9902-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>

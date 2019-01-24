---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 334bab97a04ed464dce6944692b04a9ed1295296
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613814"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="d311e-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="d311e-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="d311e-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="d311e-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d311e-104">语法</span><span class="sxs-lookup"><span data-stu-id="d311e-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d311e-105">方法</span><span class="sxs-lookup"><span data-stu-id="d311e-105">Methods</span></span>  
 <span data-ttu-id="d311e-106">MustUnderstandBehavior 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="d311e-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d311e-107">Properties</span><span class="sxs-lookup"><span data-stu-id="d311e-107">Properties</span></span>  
 <span data-ttu-id="d311e-108">MustUnderstandBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="d311e-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="d311e-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="d311e-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="d311e-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="d311e-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="d311e-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d311e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d311e-112">如果为 `true`，则所有具有 `MustUnderstand` 属性的未处理 SOAP 标头将导致引发异常的行为。</span><span class="sxs-lookup"><span data-stu-id="d311e-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d311e-113">要求</span><span class="sxs-lookup"><span data-stu-id="d311e-113">Requirements</span></span>  
  
|<span data-ttu-id="d311e-114">MOF</span><span class="sxs-lookup"><span data-stu-id="d311e-114">MOF</span></span>|<span data-ttu-id="d311e-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="d311e-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d311e-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="d311e-116">Namespace</span></span>|<span data-ttu-id="d311e-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="d311e-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d311e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d311e-118">See also</span></span>
- <xref:System.ServiceModel.Description.MustUnderstandBehavior>

---
title: 如何：在 Visual Basic 中读取应用程序设置
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 032e06e674f2298d68f879f3ad474c79e3ff02db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659487"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a><span data-ttu-id="b8bea-102">如何：在 Visual Basic 中读取应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b8bea-102">How to: Read Application Settings in Visual Basic</span></span>
<span data-ttu-id="b8bea-103">可以通过访问 `My.Settings` 对象上用户设置的属性来读取该设置。</span><span class="sxs-lookup"><span data-stu-id="b8bea-103">You can read a user setting by accessing the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="b8bea-104">`My.Settings` 对象将每个设置公开为一个属性。</span><span class="sxs-lookup"><span data-stu-id="b8bea-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="b8bea-105">属性名称就是设置的名称，属性类型就是设置类型。</span><span class="sxs-lookup"><span data-stu-id="b8bea-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="b8bea-106">设置的“范围”指示属性是否为只读；“应用程序”范围设置的属性是只读属性，而“用户”范围设置的属性是读-写属性。</span><span class="sxs-lookup"><span data-stu-id="b8bea-106">The setting's **Scope** indicates if the property is read-only; the property for an **Application** scope setting is read-only, while the property for a **User** scope setting is read-write.</span></span> <span data-ttu-id="b8bea-107">有关详细信息，请参阅 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)。</span><span class="sxs-lookup"><span data-stu-id="b8bea-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8bea-108">示例</span><span class="sxs-lookup"><span data-stu-id="b8bea-108">Example</span></span>  
 <span data-ttu-id="b8bea-109">此示例显示 `Nickname` 设置的值。</span><span class="sxs-lookup"><span data-stu-id="b8bea-109">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 <span data-ttu-id="b8bea-110">若要使此示例正常工作，应用程序必须具有类型为 `String` 的 `Nickname` 设置。</span><span class="sxs-lookup"><span data-stu-id="b8bea-110">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span> <span data-ttu-id="b8bea-111">有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="b8bea-111">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8bea-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8bea-112">See also</span></span>
- [<span data-ttu-id="b8bea-113">My.Settings 对象</span><span class="sxs-lookup"><span data-stu-id="b8bea-113">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="b8bea-114">如何：在 Visual Basic 中更改用户设置</span><span class="sxs-lookup"><span data-stu-id="b8bea-114">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="b8bea-115">如何：在 Visual Basic 中暂留用户设置</span><span class="sxs-lookup"><span data-stu-id="b8bea-115">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="b8bea-116">如何：在 Visual Basic 中为用户设置创建属性网格</span><span class="sxs-lookup"><span data-stu-id="b8bea-116">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="b8bea-117">管理应用程序设置 (.NET)</span><span class="sxs-lookup"><span data-stu-id="b8bea-117">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

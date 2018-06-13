---
title: 如何：在 Visual Basic 中读取应用程序设置
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 3de6e59c2a69c430a0376ef36f8ce52e57f5f6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585663"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a><span data-ttu-id="1e1fd-102">如何：在 Visual Basic 中读取应用程序设置</span><span class="sxs-lookup"><span data-stu-id="1e1fd-102">How to: Read Application Settings in Visual Basic</span></span>
<span data-ttu-id="1e1fd-103">可以通过访问 `My.Settings` 对象上用户设置的属性来读取该设置。</span><span class="sxs-lookup"><span data-stu-id="1e1fd-103">You can read a user setting by accessing the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="1e1fd-104">`My.Settings` 对象将每个设置公开为一个属性。</span><span class="sxs-lookup"><span data-stu-id="1e1fd-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="1e1fd-105">属性名称就是设置的名称，属性类型就是设置类型。</span><span class="sxs-lookup"><span data-stu-id="1e1fd-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="1e1fd-106">设置的“范围”指示属性是否为只读；“应用程序”范围设置的属性是只读属性，而“用户”范围设置的属性是读-写属性。</span><span class="sxs-lookup"><span data-stu-id="1e1fd-106">The setting's **Scope** indicates if the property is read-only; the property for an **Application** scope setting is read-only, while the property for a **User** scope setting is read-write.</span></span> <span data-ttu-id="1e1fd-107">有关详细信息，请参阅 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)。</span><span class="sxs-lookup"><span data-stu-id="1e1fd-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e1fd-108">示例</span><span class="sxs-lookup"><span data-stu-id="1e1fd-108">Example</span></span>  
 <span data-ttu-id="1e1fd-109">此示例显示 `Nickname` 设置的值。</span><span class="sxs-lookup"><span data-stu-id="1e1fd-109">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 <span data-ttu-id="1e1fd-110">若要使此示例正常工作，应用程序必须具有类型为 `String` 的 `Nickname` 设置。</span><span class="sxs-lookup"><span data-stu-id="1e1fd-110">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span> <span data-ttu-id="1e1fd-111">有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="1e1fd-111">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e1fd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e1fd-112">See Also</span></span>  
 [<span data-ttu-id="1e1fd-113">My.Settings 对象</span><span class="sxs-lookup"><span data-stu-id="1e1fd-113">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="1e1fd-114">如何：在 Visual Basic 中更改用户设置</span><span class="sxs-lookup"><span data-stu-id="1e1fd-114">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="1e1fd-115">如何：在 Visual Basic 中保存用户设置</span><span class="sxs-lookup"><span data-stu-id="1e1fd-115">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="1e1fd-116">如何：在 Visual Basic 中创建用户设置的属性网格</span><span class="sxs-lookup"><span data-stu-id="1e1fd-116">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="1e1fd-117">管理应用程序设置 (.NET)</span><span class="sxs-lookup"><span data-stu-id="1e1fd-117">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

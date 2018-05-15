---
title: 活动本地化
ms.date: 03/30/2017
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
ms.openlocfilehash: 23a6d5c2ed202f030397eb70382896468a68a724
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="activity-localization"></a><span data-ttu-id="306c2-102">活动本地化</span><span class="sxs-lookup"><span data-stu-id="306c2-102">Activity Localization</span></span>
<span data-ttu-id="306c2-103">当工作流应用程序和组件可能要根据其他区域文化和语言进行本地化时，应使用资源字符串，以便无需重新编译即可对它们进行本地化。</span><span class="sxs-lookup"><span data-stu-id="306c2-103">When workflow applications and components have the potential to be localized into other cultures and languages, resource strings should be used so that they can be localized without recompiling.</span></span>  
  
## <a name="activity-localization"></a><span data-ttu-id="306c2-104">活动本地化</span><span class="sxs-lookup"><span data-stu-id="306c2-104">Activity Localization</span></span>  
 <span data-ttu-id="306c2-105">与必须本地化（针对不同的语言和区域文化发布不同的版本）的所有应用程序一样，向用户显示的任何字符串不应直接放在代码中，而应存储在某个资源文件中。</span><span class="sxs-lookup"><span data-stu-id="306c2-105">As with all applications that must be localized (released in different versions for different languages and cultures), any strings that are displayed to the user should not be put directly in code, but rather stored in a resource file.</span></span> <span data-ttu-id="306c2-106">然后可以通过访问这些字符串<!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`。</span><span class="sxs-lookup"><span data-stu-id="306c2-106">The strings can then be accessed through <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span></span> <span data-ttu-id="306c2-107">如果您开发的某个组件以多种语言分发，则还需要对活动验证消息、用户定义的跟踪数据、跟踪消息以及错误消息使用资源字符串。</span><span class="sxs-lookup"><span data-stu-id="306c2-107">If you are developing a component that is distributed in several languages, you also want to use resource strings for activity validation messages, user-defined tracking data, tracing messages, and error messages as well.</span></span>  
  
 <span data-ttu-id="306c2-108">下面的练习演示如何使用资源文件。</span><span class="sxs-lookup"><span data-stu-id="306c2-108">The following exercise demonstrates how to use a resource file.</span></span>  
  
#### <a name="using-resource-files-for-localized-strings"></a><span data-ttu-id="306c2-109">对本地化的字符串使用资源文件</span><span class="sxs-lookup"><span data-stu-id="306c2-109">Using resource files for localized strings</span></span>  
  
1.  <span data-ttu-id="306c2-110">在[!INCLUDE[vs2010](../../../includes/vs2010-md.md)]，右键单击你的项目中**解决方案资源管理器**和选择**添加...**，**新建项...**.</span><span class="sxs-lookup"><span data-stu-id="306c2-110">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], right-click your project in **Solution Explorer** and select **Add…**, **New Item…**.</span></span>  
  
2.  <span data-ttu-id="306c2-111">选择**资源文件**并将文件命名为 ErrorResources.resx。</span><span class="sxs-lookup"><span data-stu-id="306c2-111">Select **Resources File** and name the file ErrorResources.resx.</span></span> <span data-ttu-id="306c2-112">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="306c2-112">Click **Add**.</span></span>  
  
3.  <span data-ttu-id="306c2-113">打开该资源文件。</span><span class="sxs-lookup"><span data-stu-id="306c2-113">Open the resource file.</span></span> <span data-ttu-id="306c2-114">添加一个新项**名称**为 ErrorString 和**值**的"活动无效。"</span><span class="sxs-lookup"><span data-stu-id="306c2-114">Add a new entry with a **Name** of ErrorString and a **Value** of "The activity is not valid."</span></span>  
  
4.  <span data-ttu-id="306c2-115">向类中添加以下 `using` 声明。</span><span class="sxs-lookup"><span data-stu-id="306c2-115">Add the following `using` statements to your class.</span></span>  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  <span data-ttu-id="306c2-116">在项目中创建一个资源管理器。</span><span class="sxs-lookup"><span data-stu-id="306c2-116">Create a resource manager in your project.</span></span>  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  <span data-ttu-id="306c2-117">从资源管理器中获取字符串，该字符串在资源管理器中是必需的。</span><span class="sxs-lookup"><span data-stu-id="306c2-117">Get the string from the resource manager where it is required.</span></span>  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 <span data-ttu-id="306c2-118">以下代码示例演示了如何在 <xref:System.Activities.Activity.CacheMetadata%2A> 方法中使用本地化的字符串。</span><span class="sxs-lookup"><span data-stu-id="306c2-118">The following code sample demonstrates how to utilize localized strings in the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span>  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```

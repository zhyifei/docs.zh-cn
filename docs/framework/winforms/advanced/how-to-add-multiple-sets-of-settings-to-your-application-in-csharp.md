---
title: 如何：向应用程序中添加多组设置C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 43402d8a1b0b1ca26e656be1424a5fa341ac4728
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719645"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="b0908-102">如何：将多组设置添加到你在 C 中的应用程序\#</span><span class="sxs-lookup"><span data-stu-id="b0908-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>
<span data-ttu-id="b0908-103">在某些情况下，你可能想要的应用程序中有多组设置。</span><span class="sxs-lookup"><span data-stu-id="b0908-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="b0908-104">例如，如果你正在开发的应用设置的特定组的地方频繁进行更改，可能会比较明智的做法其全都分成单个文件，以便可以成批，替换该文件保持不受影响的其他设置。</span><span class="sxs-lookup"><span data-stu-id="b0908-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="b0908-105">Visual Studio，可将多组设置添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="b0908-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="b0908-106">可以通过 Properties.Settings 对象访问更多组设置。</span><span class="sxs-lookup"><span data-stu-id="b0908-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="b0908-107">若要将一组额外的设置添加到你的应用程序</span><span class="sxs-lookup"><span data-stu-id="b0908-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1.  <span data-ttu-id="b0908-108">从“项目”菜单中选择“添加新项”。</span><span class="sxs-lookup"><span data-stu-id="b0908-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="b0908-109">此时将打开“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="b0908-109">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="b0908-110">在中**添加新项**对话框中，选择**设置文件**，键入该文件的名称，然后单击**添加**将新的设置文件添加到你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b0908-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3.  <span data-ttu-id="b0908-111">在中**解决方案资源管理器**，将为新的设置文件拖放**属性**文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0908-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="b0908-112">这允许你设置可在代码中使用新设置。</span><span class="sxs-lookup"><span data-stu-id="b0908-112">This allows your new settings to be available in code.</span></span>  
  
4.  <span data-ttu-id="b0908-113">添加和使用此文件中的设置，也可以是任何其他设置文件。</span><span class="sxs-lookup"><span data-stu-id="b0908-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="b0908-114">您可以访问此组通过 Properties.Settings 对象的设置。</span><span class="sxs-lookup"><span data-stu-id="b0908-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0908-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0908-115">See also</span></span>
- [<span data-ttu-id="b0908-116">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="b0908-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="b0908-117">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="b0908-117">Application Settings Overview</span></span>](application-settings-overview.md)

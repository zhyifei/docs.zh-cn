---
title: 如何：向应用程序添加多组设置 (C#)
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: c6842d11c04e905d42734af939f2c3f0cfeacd47
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040128"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="50ee9-102">如何：将多组设置添加到应用程序中的 C\#</span><span class="sxs-lookup"><span data-stu-id="50ee9-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="50ee9-103">在某些情况下, 你可能希望在应用程序中包含多组设置。</span><span class="sxs-lookup"><span data-stu-id="50ee9-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="50ee9-104">例如, 如果你正在开发一个应用程序, 其中一组特定的设置需要频繁更改, 则可能会将它们全部隔开到一个文件中, 以便可以将该文件替换为批发, 而不影响其他设置。</span><span class="sxs-lookup"><span data-stu-id="50ee9-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="50ee9-105">Visual Studio 允许你向项目添加多个设置集。</span><span class="sxs-lookup"><span data-stu-id="50ee9-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="50ee9-106">可以通过`Properties.Settings`对象访问其他设置集。</span><span class="sxs-lookup"><span data-stu-id="50ee9-106">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="50ee9-107">添加一组其他设置</span><span class="sxs-lookup"><span data-stu-id="50ee9-107">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="50ee9-108">在 Visual Studio 的 "**项目**" 菜单中, 选择 "**添加新项**"。</span><span class="sxs-lookup"><span data-stu-id="50ee9-108">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="50ee9-109">此时将打开“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="50ee9-109">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="50ee9-110">在 "**添加新项**" 对话框中, 选择 "**设置文件**", 输入文件的名称, 然后单击 "**添加**" 以将新的设置文件添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="50ee9-110">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="50ee9-111">在**解决方案资源管理器**中, 将新的设置文件拖到**Properties**文件夹中。</span><span class="sxs-lookup"><span data-stu-id="50ee9-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="50ee9-112">这允许您的新设置在代码中可用。</span><span class="sxs-lookup"><span data-stu-id="50ee9-112">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="50ee9-113">像添加任何其他设置文件一样, 在此文件中添加和使用设置。</span><span class="sxs-lookup"><span data-stu-id="50ee9-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="50ee9-114">可以通过`Properties.Settings`对象访问这组设置。</span><span class="sxs-lookup"><span data-stu-id="50ee9-114">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="50ee9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="50ee9-115">See also</span></span>

- [<span data-ttu-id="50ee9-116">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="50ee9-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="50ee9-117">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="50ee9-117">Application Settings Overview</span></span>](application-settings-overview.md)

---
title: "类型提供程序疑难解答"
description: "发现问题的最有可能，若要在 F # 中使用类型提供程序时遇到的潜在的解决方案。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 44533045-9862-43c5-81d9-3e05157e975a
ms.openlocfilehash: 2b54454d7950dfdd6512d849fd739f505ef3317d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-type-providers"></a><span data-ttu-id="63451-104">类型提供程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="63451-104">Troubleshooting Type Providers</span></span>

<span data-ttu-id="63451-105">本主题介绍并提供最有可能，若要使用类型提供程序时遇到的问题的潜在解决方案。</span><span class="sxs-lookup"><span data-stu-id="63451-105">This topic describes and provides potential solutions for the problems that you are most likely to encounter when you use type providers.</span></span>


## <a name="possible-problems-with-type-providers"></a><span data-ttu-id="63451-106">用类型提供程序可能存在的问题</span><span class="sxs-lookup"><span data-stu-id="63451-106">Possible Problems with Type Providers</span></span>
<span data-ttu-id="63451-107">如果你遇到问题，当您使用类型提供程序时，你可以查看下表中的最常见的解决方案。</span><span class="sxs-lookup"><span data-stu-id="63451-107">If you encounter a problem when you work with type providers, you can review the following table for the most common solutions.</span></span>



|<span data-ttu-id="63451-108">问题</span><span class="sxs-lookup"><span data-stu-id="63451-108">Problem</span></span>|<span data-ttu-id="63451-109">建议的操作</span><span class="sxs-lookup"><span data-stu-id="63451-109">Suggested Actions</span></span>|
|-------|-----------------|
|<span data-ttu-id="63451-110">**架构更改**。</span><span class="sxs-lookup"><span data-stu-id="63451-110">**Schema Changes**.</span></span> <span data-ttu-id="63451-111">类型提供程序的效果最佳的数据源架构时保持不变。</span><span class="sxs-lookup"><span data-stu-id="63451-111">Type providers work best  when the data source schema is stable.</span></span> <span data-ttu-id="63451-112">如果你添加的数据的表或列，或更改该架构的另一个，类型提供程序无法自动识别这些更改。</span><span class="sxs-lookup"><span data-stu-id="63451-112">If you add a data table or column or make another change to that schema, the type provider doesn’t automatically recognize these changes.</span></span>|<span data-ttu-id="63451-113">清理或重新生成项目。</span><span class="sxs-lookup"><span data-stu-id="63451-113">Clean or rebuild the project.</span></span> <span data-ttu-id="63451-114">若要清除该项目，选择**生成**，**清理** *ProjectName*菜单栏上。</span><span class="sxs-lookup"><span data-stu-id="63451-114">To clean the project, choose **Build**, **Clean** *ProjectName* on the menu bar.</span></span> <span data-ttu-id="63451-115">若要重新生成项目，选择**生成**，**重新生成** *ProjectName*菜单栏上。</span><span class="sxs-lookup"><span data-stu-id="63451-115">To rebuild the project, choose **Build**, **Rebuild** *ProjectName* on the menu bar.</span></span> <span data-ttu-id="63451-116">这些操作重置所有类型提供程序状态，并强制要重新连接到数据源并获取更新的架构信息的提供程序。</span><span class="sxs-lookup"><span data-stu-id="63451-116">These actions reset all type provider state and force the provider to reconnect to the data source and obtain updated schema information.</span></span>|
|<span data-ttu-id="63451-117">**连接失败**。</span><span class="sxs-lookup"><span data-stu-id="63451-117">**Connection Failure**.</span></span> <span data-ttu-id="63451-118">URL 或连接字符串不正确、 网络已关闭，或者数据源或服务不可用。</span><span class="sxs-lookup"><span data-stu-id="63451-118">The URL or connection string is incorrect, the network is down, or the data source or service is unavailable.</span></span>|<span data-ttu-id="63451-119">对于 web 服务或 OData 服务，你可以尝试在 Internet Explorer 中以验证是否 URL 正确无误且服务可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="63451-119">For a web service or OData service, you can try the URL in Internet Explorer to verify whether the URL is correct and the service is available.</span></span> <span data-ttu-id="63451-120">对于数据库连接字符串，你可以使用中的数据连接工具**服务器资源管理器**以验证是否是有效的连接字符串和数据库是否可用。</span><span class="sxs-lookup"><span data-stu-id="63451-120">For a database connection string, you can use the data connection tools in **Server Explorer** to verify whether the connection string is valid and the database is available.</span></span> <span data-ttu-id="63451-121">还原你的连接之后，你应然后清理或重新生成项目，以便类型提供程序将重新连接到网络。</span><span class="sxs-lookup"><span data-stu-id="63451-121">After you restore your connection, you should then clean or rebuild the project so that the type provider will reconnect to the network.</span></span>|
|<span data-ttu-id="63451-122">**不是有效的凭据**。</span><span class="sxs-lookup"><span data-stu-id="63451-122">**Not Valid Credentials**.</span></span> <span data-ttu-id="63451-123">您必须具有有效权限的数据源或 web 服务。</span><span class="sxs-lookup"><span data-stu-id="63451-123">You must have valid permissions for the data source or web service.</span></span>|<span data-ttu-id="63451-124">对于 SQL 连接，用户名和连接字符串或配置文件中指定的密码必须是有效的数据库。</span><span class="sxs-lookup"><span data-stu-id="63451-124">For a SQL connection, the username and the password that are specified in the connection string or configuration file must be valid for the database.</span></span> <span data-ttu-id="63451-125">如果使用 Windows 身份验证，你必须具有对数据库的访问。</span><span class="sxs-lookup"><span data-stu-id="63451-125">If you are using Windows Authentication, you must have access to the database.</span></span> <span data-ttu-id="63451-126">数据库管理员可以标识所需的权限对每个数据库和数据库中的每个元素的访问。</span><span class="sxs-lookup"><span data-stu-id="63451-126">The database administrator can identify what permissions you need for access to each database and each element within a database.</span></span><br /><br /><span data-ttu-id="63451-127">对于 web 服务或数据服务，你必须具有相应凭据。</span><span class="sxs-lookup"><span data-stu-id="63451-127">For a web service or a data service, you must have appropriate credentials.</span></span> <span data-ttu-id="63451-128">大多数类型提供程序提供 DataContext 对象，它包含你可以使用相应的用户名和访问密钥设置的凭据属性。</span><span class="sxs-lookup"><span data-stu-id="63451-128">Most type providers provide a DataContext object, which contains a Credentials property that you can set with the appropriate username and access key.</span></span>|
|<span data-ttu-id="63451-129">**不是有效的路径**。</span><span class="sxs-lookup"><span data-stu-id="63451-129">**Not Valid Path**.</span></span> <span data-ttu-id="63451-130">文件的路径无效。</span><span class="sxs-lookup"><span data-stu-id="63451-130">A path to a file was not valid.</span></span>|<span data-ttu-id="63451-131">验证是否路径正确无误，并且该文件存在。</span><span class="sxs-lookup"><span data-stu-id="63451-131">Verify whether the path is correct and the file exists.</span></span> <span data-ttu-id="63451-132">此外，你必须相应地 quote 路径中的任何 backlashes 或使用原义字符串或三引号字符串。</span><span class="sxs-lookup"><span data-stu-id="63451-132">In addition, you must either quote any backlashes in the path appropriately or use a verbatim string or triple-quoted string.</span></span>|

## <a name="see-also"></a><span data-ttu-id="63451-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63451-133">See Also</span></span>
[<span data-ttu-id="63451-134">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="63451-134">Type Providers</span></span>](index.md)

---
title: 联机备份
ms.date: 12/13/2019
description: 了解如何使用 SQLite 的联机备份功能。
ms.openlocfilehash: 885aa2c5555b58deb2551c0a4e6933742a093457
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450344"
---
# <a name="online-backup"></a><span data-ttu-id="9e90e-103">联机备份</span><span class="sxs-lookup"><span data-stu-id="9e90e-103">Online backup</span></span>

<span data-ttu-id="9e90e-104">SQLite 可以在应用运行时备份数据库文件。</span><span class="sxs-lookup"><span data-stu-id="9e90e-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="9e90e-105">此功能在 `SqliteConnection`上的 <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> 方法中提供。</span><span class="sxs-lookup"><span data-stu-id="9e90e-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="9e90e-106">目前，`BackupDatabase` 会尽快备份数据库，并阻止其他连接写入数据库。</span><span class="sxs-lookup"><span data-stu-id="9e90e-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="9e90e-107">问题[#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834)将提供备用 API 来备份后台数据库，并允许其他连接中断备份并写入数据库。</span><span class="sxs-lookup"><span data-stu-id="9e90e-107">Issue [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="9e90e-108">如果你感兴趣，请提供有关该问题的反馈。</span><span class="sxs-lookup"><span data-stu-id="9e90e-108">If you're interested, provide feedback on the issue.</span></span>

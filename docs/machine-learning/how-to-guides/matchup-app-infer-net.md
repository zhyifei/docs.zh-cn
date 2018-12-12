---
title: 使用 Infer.NET 和概率性编程创建游戏匹配列表
description: 了解如何使用概率性编程和 Infer.NET 创建基于简化版 TrueSkill 的游戏匹配列表应用。
ms.date: 10/04/2018
ms.custom: mvc,how-to
ms.openlocfilehash: ceeb0f43e03c7ce93f105498f44bf243eec86bbf
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152458"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a><span data-ttu-id="93046-103">使用 Infer.NET 和概率性编程创建游戏匹配列表</span><span class="sxs-lookup"><span data-stu-id="93046-103">Create a game match up list app with Infer.NET and probabilistic programming</span></span>

<span data-ttu-id="93046-104">此操作指南介绍了如何使用 Infer.NET 进行概率性编程。</span><span class="sxs-lookup"><span data-stu-id="93046-104">This how-to guide teaches you about probabilistic programming using Infer.NET.</span></span> <span data-ttu-id="93046-105">概率性编程是一种将自定义模型表示为计算机程序的机器学习方法。</span><span class="sxs-lookup"><span data-stu-id="93046-105">Probabilistic programming is a machine learning approach where custom models are expressed as computer programs.</span></span> <span data-ttu-id="93046-106">借助它可以在模型中包含专业知识，使机器学习系统更易理解。</span><span class="sxs-lookup"><span data-stu-id="93046-106">It allows for incorporating domain knowledge in the models and makes the machine learning system more interpretable.</span></span> <span data-ttu-id="93046-107">它还支持在线推断，即在新数据到达时进行学习的过程。</span><span class="sxs-lookup"><span data-stu-id="93046-107">It also supports online inference – the process of learning as new data arrives.</span></span> <span data-ttu-id="93046-108">Azure、Xbox 及必应中的多种 Microsoft 产品均使用了 Infer.NET。</span><span class="sxs-lookup"><span data-stu-id="93046-108">Infer.NET is used in various products at Microsoft in Azure, Xbox, and Bing.</span></span>

## <a name="what-is-probabilistic-programming"></a><span data-ttu-id="93046-109">什么是概率性编程？</span><span class="sxs-lookup"><span data-stu-id="93046-109">What is probabilistic programming?</span></span>

<span data-ttu-id="93046-110">借助概率性编程，可创建真实过程的统计模型。</span><span class="sxs-lookup"><span data-stu-id="93046-110">Probabilistic programming allows us to create statistical models of real-world processes.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="93046-111">系统必备</span><span class="sxs-lookup"><span data-stu-id="93046-111">Prerequisites</span></span>

- <span data-ttu-id="93046-112">本地开发环境设置</span><span class="sxs-lookup"><span data-stu-id="93046-112">Local development environment setup</span></span>

  <span data-ttu-id="93046-113">此操作指南要求有一台可用于进行开发的计算机。</span><span class="sxs-lookup"><span data-stu-id="93046-113">This how-to guide expects you to have a machine you can use for development.</span></span> <span data-ttu-id="93046-114">.NET [10 分钟入门](https://www.microsoft.com/net/core)教程介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="93046-114">The .NET [Get Started in 10 minutes](https://www.microsoft.com/net/core) tutorial has instructions for setting up your local development environment on Mac, PC, or Linux.</span></span>

## <a name="create-your-app"></a><span data-ttu-id="93046-115">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="93046-115">Create your app</span></span>

1. <span data-ttu-id="93046-116">打开一个新的命令提示符，并运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="93046-116">Open a new command prompt and run the following commands:</span></span>

```console
dotnet new console -o myApp
cd myApp
```

<span data-ttu-id="93046-117">`dotnet` 命令将创建 `console` 类型的 `new` 应用程序。</span><span class="sxs-lookup"><span data-stu-id="93046-117">The `dotnet` command creates a `new` application of type `console`.</span></span> <span data-ttu-id="93046-118">`-o` 参数将创建名称为 `myApp` 的目录，会在其中存储应用并填充所需的文件。</span><span class="sxs-lookup"><span data-stu-id="93046-118">The `-o` parameter creates a directory named `myApp` where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="93046-119">`cd myApp` 命令会将你转到新创建的应用目录。</span><span class="sxs-lookup"><span data-stu-id="93046-119">The `cd myApp` command puts you into the newly created app directory.</span></span>

## <a name="install-infernet-package"></a><span data-ttu-id="93046-120">安装 Infer.NET 包</span><span class="sxs-lookup"><span data-stu-id="93046-120">Install Infer.NET package</span></span>

<span data-ttu-id="93046-121">需安装 `Microsoft.ML.Probabilistic.Compiler` 包才能使用 Infer.NET。</span><span class="sxs-lookup"><span data-stu-id="93046-121">To use Infer.NET, you need to install the `Microsoft.ML.Probabilistic.Compiler` package.</span></span> <span data-ttu-id="93046-122">在命令提示符中运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="93046-122">In your command prompt, run the following command:</span></span>

```console
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a><span data-ttu-id="93046-123">设计模型</span><span class="sxs-lookup"><span data-stu-id="93046-123">Design your model</span></span>

<span data-ttu-id="93046-124">示例使用在 Office 中进行的乒乓球或桌上足球比赛。</span><span class="sxs-lookup"><span data-stu-id="93046-124">The example sample uses table tennis or foosball matches played in the office.</span></span> <span data-ttu-id="93046-125">我们具有参赛者的信息和每场比赛的结果。</span><span class="sxs-lookup"><span data-stu-id="93046-125">We have the participants and outcome of each match.</span></span>  <span data-ttu-id="93046-126">我们想要通过此数据推断玩家的实力。</span><span class="sxs-lookup"><span data-stu-id="93046-126">We want to infer the player's skills from this data.</span></span> <span data-ttu-id="93046-127">假设每位玩家的潜在实力呈正态分布，且他们在给定比赛中的表现是此实力受干扰后的状态。</span><span class="sxs-lookup"><span data-stu-id="93046-127">We’ll assume that each player has a normally distributed latent skill and their performance in a given match is a noisy version of this skill.</span></span> <span data-ttu-id="93046-128">此数据会将胜者的表现约束在优于败者的表现。</span><span class="sxs-lookup"><span data-stu-id="93046-128">The data constrains the winner’s performance to be greater than the loser’s performance.</span></span> <span data-ttu-id="93046-129">这是热门的 [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/) 模型的简化版，此模型也支持团队、平局及其他扩展项。</span><span class="sxs-lookup"><span data-stu-id="93046-129">This is a simplified version of the popular [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/) model, which also supports teams, draws, and other extensions.</span></span> <span data-ttu-id="93046-130">热销的 Halo 和 Gears of War 游戏中的比赛安排使用了此模型的[高级版](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/)。</span><span class="sxs-lookup"><span data-stu-id="93046-130">An [advanced version](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) of this model is used for matchmaking in the best-selling game titles Halo and Gears of War.</span></span>

<span data-ttu-id="93046-131">我们需要列出所推断玩家的实力及其方差（实力不确定性的度量值）。</span><span class="sxs-lookup"><span data-stu-id="93046-131">We need to list the inferred player skills, alongside with their variance – the measure of uncertainty around the skills.</span></span>

<span data-ttu-id="93046-132">*游戏结果示例数据*</span><span class="sxs-lookup"><span data-stu-id="93046-132">*Game result sample data*</span></span>

<span data-ttu-id="93046-133">游戏</span><span class="sxs-lookup"><span data-stu-id="93046-133">Game</span></span> |<span data-ttu-id="93046-134">胜者</span><span class="sxs-lookup"><span data-stu-id="93046-134">Winner</span></span> | <span data-ttu-id="93046-135">败者</span><span class="sxs-lookup"><span data-stu-id="93046-135">Loser</span></span>
---------|----------|---------
 <span data-ttu-id="93046-136">1</span><span class="sxs-lookup"><span data-stu-id="93046-136">1</span></span> | <span data-ttu-id="93046-137">玩家 0</span><span class="sxs-lookup"><span data-stu-id="93046-137">Player 0</span></span> | <span data-ttu-id="93046-138">玩家 1</span><span class="sxs-lookup"><span data-stu-id="93046-138">Player 1</span></span>
 <span data-ttu-id="93046-139">2</span><span class="sxs-lookup"><span data-stu-id="93046-139">2</span></span> | <span data-ttu-id="93046-140">玩家 0</span><span class="sxs-lookup"><span data-stu-id="93046-140">Player 0</span></span> | <span data-ttu-id="93046-141">玩家 3</span><span class="sxs-lookup"><span data-stu-id="93046-141">Player 3</span></span>
 <span data-ttu-id="93046-142">3</span><span class="sxs-lookup"><span data-stu-id="93046-142">3</span></span> | <span data-ttu-id="93046-143">玩家 0</span><span class="sxs-lookup"><span data-stu-id="93046-143">Player 0</span></span> | <span data-ttu-id="93046-144">玩家 4</span><span class="sxs-lookup"><span data-stu-id="93046-144">Player 4</span></span>
 <span data-ttu-id="93046-145">4</span><span class="sxs-lookup"><span data-stu-id="93046-145">4</span></span> | <span data-ttu-id="93046-146">玩家 1</span><span class="sxs-lookup"><span data-stu-id="93046-146">Player 1</span></span> | <span data-ttu-id="93046-147">玩家 2</span><span class="sxs-lookup"><span data-stu-id="93046-147">Player 2</span></span>
 <span data-ttu-id="93046-148">5</span><span class="sxs-lookup"><span data-stu-id="93046-148">5</span></span> | <span data-ttu-id="93046-149">玩家 3</span><span class="sxs-lookup"><span data-stu-id="93046-149">Player 3</span></span> | <span data-ttu-id="93046-150">玩家 1</span><span class="sxs-lookup"><span data-stu-id="93046-150">Player 1</span></span>
 <span data-ttu-id="93046-151">6</span><span class="sxs-lookup"><span data-stu-id="93046-151">6</span></span> | <span data-ttu-id="93046-152">玩家 4</span><span class="sxs-lookup"><span data-stu-id="93046-152">Player 4</span></span> | <span data-ttu-id="93046-153">玩家 2</span><span class="sxs-lookup"><span data-stu-id="93046-153">Player 2</span></span>

<span data-ttu-id="93046-154">仔细观察示例数据会发现玩家 3 和玩家 4 分别输赢过一次。</span><span class="sxs-lookup"><span data-stu-id="93046-154">With a closer look at the sample data, you’ll notice that players 3 and 4 both have one win and one loss.</span></span> <span data-ttu-id="93046-155">我们来看下使用概率性编程时的排名。</span><span class="sxs-lookup"><span data-stu-id="93046-155">Let's see what the rankings look like using probabilistic programming.</span></span> <span data-ttu-id="93046-156">还会注意到有一位玩家 0，因为对于开发人员而言，甚至 Office 匹配列表都是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="93046-156">Notice also there is a player zero because even office match up lists are zero based to us developers.</span></span>

## <a name="write-some-code"></a><span data-ttu-id="93046-157">编写代码</span><span class="sxs-lookup"><span data-stu-id="93046-157">Write some code</span></span>

<span data-ttu-id="93046-158">设计模型后，就可以使用 Infer.NET 建模 API 将其表示为概率性程序。</span><span class="sxs-lookup"><span data-stu-id="93046-158">Having designed the model, it’s time to express it as a probabilistic program using the Infer.NET modeling API.</span></span> <span data-ttu-id="93046-159">在常用的文本编辑器中，打开 `Program.cs`，并将其所有内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="93046-159">Open `Program.cs` in your favorite text editor and replace all of its contents with the following code:</span></span>

```csharp
namespace myApp

{
    using System;
    using System.Linq;
    using Microsoft.ML.Probabilistic;
    using Microsoft.ML.Probabilistic.Distributions;
    using Microsoft.ML.Probabilistic.Models;

    class Program
    {

        static void Main(string[] args)
        {
            // The winner and loser in each of 6 samples games
            var winnerData = new[] { 0, 0, 0, 1, 3, 4 };
            var loserData = new[] { 1, 3, 4, 2, 1, 2 };

            // Define the statistical model as a probabilistic program 
            var game = new Range(winnerData.Length);
            var player = new Range(winnerData.Concat(loserData).Max() + 1);
            var playerSkills = Variable.Array<double>(player);
            playerSkills[player] = Variable.GaussianFromMeanAndVariance(6, 9).ForEach(player);

            var winners = Variable.Array<int>(game);
            var losers = Variable.Array<int>(game);

            using (Variable.ForEach(game))
            {
                // The player performance is a noisy version of their skill
                var winnerPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[winners[game]], 1.0);
                var loserPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[losers[game]], 1.0);

                // The winner performed better in this game
                Variable.ConstrainTrue(winnerPerformance > loserPerformance);
            }

            // Attach the data to the model
            winners.ObservedValue = winnerData;
            losers.ObservedValue = loserData;

            // Run inference
            var inferenceEngine = new InferenceEngine();
            var inferredSkills = inferenceEngine.Infer<Gaussian[]>(playerSkills);

            // The inferred skills are uncertain, which is captured in their variance
            var orderedPlayerSkills = inferredSkills
               .Select((s, i) => new { Player = i, Skill = s })
               .OrderByDescending(ps => ps.Skill.GetMean());

            foreach (var playerSkill in orderedPlayerSkills)
            {
                Console.WriteLine($"Player {playerSkill.Player} skill: {playerSkill.Skill}");
            }
        }
    }
}
```

## <a name="run-your-app"></a><span data-ttu-id="93046-160">运行你的应用</span><span class="sxs-lookup"><span data-stu-id="93046-160">Run your app</span></span>

<span data-ttu-id="93046-161">在命令提示符中运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="93046-161">In your command prompt, run the following command:</span></span>

```console
dotnet run
```

## <a name="results"></a><span data-ttu-id="93046-162">结果</span><span class="sxs-lookup"><span data-stu-id="93046-162">Results</span></span>

<span data-ttu-id="93046-163">结果应如下所示：</span><span class="sxs-lookup"><span data-stu-id="93046-163">Your results should be similar to the following:</span></span>

```
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

<span data-ttu-id="93046-164">请注意，在结果中根据我们的模型玩家 3 排名略高于玩家 4。</span><span class="sxs-lookup"><span data-stu-id="93046-164">In the results, notice that player 3 ranks slightly higher than player 4 according to our model.</span></span> <span data-ttu-id="93046-165">因为玩家 3 战胜了玩家 1 的意义大于玩家 4 战胜玩家 2 的意义 – 请注意玩家 1 打败了玩家 2.</span><span class="sxs-lookup"><span data-stu-id="93046-165">That’s because the victory of player 3 over player 1 is more significant than the victory of player 4 over player 2 – note that player 1 beats player 2.</span></span> <span data-ttu-id="93046-166">玩家 0 是总冠军！</span><span class="sxs-lookup"><span data-stu-id="93046-166">Player 0 is the overall champ!</span></span>  

## <a name="keep-learning"></a><span data-ttu-id="93046-167">继续学习</span><span class="sxs-lookup"><span data-stu-id="93046-167">Keep learning</span></span>

<span data-ttu-id="93046-168">设计统计模型本身就是一种技能。</span><span class="sxs-lookup"><span data-stu-id="93046-168">Designing statistical models is a skill on its own.</span></span> <span data-ttu-id="93046-169">Microsoft Research Cambridge 团队曾编写过一本[免费的在线书籍](http://mbmlbook.com/)，其中简要介绍了此文。</span><span class="sxs-lookup"><span data-stu-id="93046-169">The Microsoft Research Cambridge team has written a [free online book](http://mbmlbook.com/), which gives a gentle introduction to the article.</span></span> <span data-ttu-id="93046-170">此书的第 3 章详细介绍了 TrueSkill 模型。</span><span class="sxs-lookup"><span data-stu-id="93046-170">Chapter 3 of this book covers the TrueSkill model in more detail.</span></span> <span data-ttu-id="93046-171">只要脑海中已有模型，即可使用 Infer.NET 网站上的[大量文档](https://dotnet.github.io/infer/)将其转换为代码。</span><span class="sxs-lookup"><span data-stu-id="93046-171">Once you have a model in mind, you can transform it into code using the [extensive documentation](https://dotnet.github.io/infer/) on the Infer.NET website.</span></span>

## <a name="next-steps"></a><span data-ttu-id="93046-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="93046-172">Next steps</span></span>

<span data-ttu-id="93046-173">查看 Infer.NET GitHub 存储库以继续学习，并找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="93046-173">Check out the Infer.NET GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="93046-174">dotnet/infer GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="93046-174">dotnet/infer GitHub repository</span></span>](https://github.com/dotnet/infer)

---
title: 线程池 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f1c92154fe62b1b6ba6981606680daf37d087f4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974867"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="44b60-102">线程池 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-102">Thread Pool ETW Events</span></span>
<span data-ttu-id="44b60-103">这些事件收集有关工作线程和 I/O 线程的信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="44b60-104">存在两组线程池事件：</span><span class="sxs-lookup"><span data-stu-id="44b60-104">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="44b60-105">[工作线程池事件](#worker-thread-pool-events)：提供有关应用程序如何使用线程池以及工作负荷如何影响并发控制的信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-105">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="44b60-106">[I/O 线程池事件](#io-thread-events)：提供有关线程池中创建、停用、恢复或终止的 I/O 线程的信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-106">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="44b60-107">工作线程池事件</span><span class="sxs-lookup"><span data-stu-id="44b60-107">Worker Thread Pool Events</span></span>
 <span data-ttu-id="44b60-108">这些事件与运行时工作线程池相关，并提供有关线程事件的通知（例如，创建或停止线程时）。</span><span class="sxs-lookup"><span data-stu-id="44b60-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="44b60-109">工作线程池使用自适应算法进行并发控制，其中的线程数基于测得的吞吐量来计算。</span><span class="sxs-lookup"><span data-stu-id="44b60-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="44b60-110">工作线程池事件可用于了解应用程序如何使用线程池，以及某些工作负荷可能会对并发控制怎样的影响。</span><span class="sxs-lookup"><span data-stu-id="44b60-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="44b60-111">ThreadPoolWorkerThreadStart 和 ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="44b60-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="44b60-112">下表显示这些事件的关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="44b60-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="44b60-113">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="44b60-113">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="44b60-114">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="44b60-114">Keyword for raising the event</span></span>|<span data-ttu-id="44b60-115">层次</span><span class="sxs-lookup"><span data-stu-id="44b60-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="44b60-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="44b60-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="44b60-117">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="44b60-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="44b60-118">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="44b60-119">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-119">Event</span></span>|<span data-ttu-id="44b60-120">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b60-120">Event ID</span></span>|<span data-ttu-id="44b60-121">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="44b60-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="44b60-122">50</span><span class="sxs-lookup"><span data-stu-id="44b60-122">50</span></span>|<span data-ttu-id="44b60-123">创建工作线程。</span><span class="sxs-lookup"><span data-stu-id="44b60-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="44b60-124">51</span><span class="sxs-lookup"><span data-stu-id="44b60-124">51</span></span>|<span data-ttu-id="44b60-125">停止工作线程。</span><span class="sxs-lookup"><span data-stu-id="44b60-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="44b60-126">52</span><span class="sxs-lookup"><span data-stu-id="44b60-126">52</span></span>|<span data-ttu-id="44b60-127">停用工作线程。</span><span class="sxs-lookup"><span data-stu-id="44b60-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="44b60-128">53</span><span class="sxs-lookup"><span data-stu-id="44b60-128">53</span></span>|<span data-ttu-id="44b60-129">停用的工作线程再次变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="44b60-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="44b60-130">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="44b60-131">字段名</span><span class="sxs-lookup"><span data-stu-id="44b60-131">Field name</span></span>|<span data-ttu-id="44b60-132">数据类型</span><span class="sxs-lookup"><span data-stu-id="44b60-132">Data type</span></span>|<span data-ttu-id="44b60-133">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="44b60-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="44b60-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="44b60-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="44b60-135">win:UInt32</span></span>|<span data-ttu-id="44b60-136">可用于处理工作的工作线程数，包括已在处理工作的工作线程。</span><span class="sxs-lookup"><span data-stu-id="44b60-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="44b60-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="44b60-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="44b60-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="44b60-138">win:UInt32</span></span>|<span data-ttu-id="44b60-139">不能用于处理工作但被保留以防之后需要更多线程的工作线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="44b60-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="44b60-140">ClrInstanceID</span></span>|<span data-ttu-id="44b60-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-141">Win:UInt16</span></span>|<span data-ttu-id="44b60-142">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44b60-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="44b60-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="44b60-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="44b60-144">这些线程池事件提供用于了解和调试线程注入（并发控制）算法行为的信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="44b60-145">这些信息由工作线程池在内部使用。</span><span class="sxs-lookup"><span data-stu-id="44b60-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="44b60-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="44b60-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="44b60-147">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="44b60-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="44b60-148">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="44b60-148">Keyword for raising the event</span></span>|<span data-ttu-id="44b60-149">层次</span><span class="sxs-lookup"><span data-stu-id="44b60-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="44b60-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="44b60-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="44b60-151">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="44b60-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="44b60-152">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="44b60-153">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-153">Event</span></span>|<span data-ttu-id="44b60-154">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b60-154">Event ID</span></span>|<span data-ttu-id="44b60-155">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="44b60-156">54</span><span class="sxs-lookup"><span data-stu-id="44b60-156">54</span></span>|<span data-ttu-id="44b60-157">指一个示例的信息收集，即具有一定并发级别的即时吞吐量测量。</span><span class="sxs-lookup"><span data-stu-id="44b60-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="44b60-158">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="44b60-159">字段名</span><span class="sxs-lookup"><span data-stu-id="44b60-159">Field name</span></span>|<span data-ttu-id="44b60-160">数据类型</span><span class="sxs-lookup"><span data-stu-id="44b60-160">Data type</span></span>|<span data-ttu-id="44b60-161">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="44b60-162">吞吐量</span><span class="sxs-lookup"><span data-stu-id="44b60-162">Throughput</span></span>|<span data-ttu-id="44b60-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-163">win:Double</span></span>|<span data-ttu-id="44b60-164">每个时间单位的完成数。</span><span class="sxs-lookup"><span data-stu-id="44b60-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="44b60-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="44b60-165">ClrInstanceID</span></span>|<span data-ttu-id="44b60-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-166">Win:UInt16</span></span>|<span data-ttu-id="44b60-167">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44b60-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="44b60-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="44b60-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="44b60-169">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="44b60-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="44b60-170">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="44b60-170">Keyword for raising the event</span></span>|<span data-ttu-id="44b60-171">层次</span><span class="sxs-lookup"><span data-stu-id="44b60-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="44b60-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="44b60-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="44b60-173">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="44b60-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="44b60-174">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="44b60-175">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-175">Event</span></span>|<span data-ttu-id="44b60-176">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b60-176">Event ID</span></span>|<span data-ttu-id="44b60-177">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="44b60-178">55</span><span class="sxs-lookup"><span data-stu-id="44b60-178">55</span></span>|<span data-ttu-id="44b60-179">当线程注入（爬山）算法确定并发级别发生更改时，在控件中记录更改。</span><span class="sxs-lookup"><span data-stu-id="44b60-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="44b60-180">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="44b60-181">字段名</span><span class="sxs-lookup"><span data-stu-id="44b60-181">Field name</span></span>|<span data-ttu-id="44b60-182">数据类型</span><span class="sxs-lookup"><span data-stu-id="44b60-182">Data type</span></span>|<span data-ttu-id="44b60-183">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="44b60-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="44b60-184">AverageThroughput</span></span>|<span data-ttu-id="44b60-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-185">win:Double</span></span>|<span data-ttu-id="44b60-186">测量示例的平均吞吐量。</span><span class="sxs-lookup"><span data-stu-id="44b60-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="44b60-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="44b60-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="44b60-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="44b60-188">win:UInt32</span></span>|<span data-ttu-id="44b60-189">新的活动工作线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="44b60-190">原因</span><span class="sxs-lookup"><span data-stu-id="44b60-190">Reason</span></span>|<span data-ttu-id="44b60-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="44b60-191">win:UInt32</span></span>|<span data-ttu-id="44b60-192">调整的原因。</span><span class="sxs-lookup"><span data-stu-id="44b60-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="44b60-193">0x00 - 预热。</span><span class="sxs-lookup"><span data-stu-id="44b60-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="44b60-194">0x01 - 初始化。</span><span class="sxs-lookup"><span data-stu-id="44b60-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="44b60-195">0x02 - 随机移动。</span><span class="sxs-lookup"><span data-stu-id="44b60-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="44b60-196">0x03 - 攀移。</span><span class="sxs-lookup"><span data-stu-id="44b60-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="44b60-197">0x04 - 更改点。</span><span class="sxs-lookup"><span data-stu-id="44b60-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="44b60-198">0x05 - 稳定。</span><span class="sxs-lookup"><span data-stu-id="44b60-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="44b60-199">0x06 - 匮乏。</span><span class="sxs-lookup"><span data-stu-id="44b60-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="44b60-200">0x07 - 线程已超时。</span><span class="sxs-lookup"><span data-stu-id="44b60-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="44b60-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="44b60-201">ClrInstanceID</span></span>|<span data-ttu-id="44b60-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-202">Win:UInt16</span></span>|<span data-ttu-id="44b60-203">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44b60-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="44b60-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="44b60-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="44b60-205">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="44b60-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="44b60-206">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="44b60-206">Keyword for raising the event</span></span>|<span data-ttu-id="44b60-207">层次</span><span class="sxs-lookup"><span data-stu-id="44b60-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="44b60-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="44b60-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="44b60-209">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="44b60-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="44b60-210">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="44b60-211">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-211">Event</span></span>|<span data-ttu-id="44b60-212">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b60-212">Event ID</span></span>|<span data-ttu-id="44b60-213">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="44b60-214">56</span><span class="sxs-lookup"><span data-stu-id="44b60-214">56</span></span>|<span data-ttu-id="44b60-215">在线程池上收集数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="44b60-216">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="44b60-217">字段名</span><span class="sxs-lookup"><span data-stu-id="44b60-217">Field name</span></span>|<span data-ttu-id="44b60-218">数据类型</span><span class="sxs-lookup"><span data-stu-id="44b60-218">Data type</span></span>|<span data-ttu-id="44b60-219">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="44b60-220">持续时间</span><span class="sxs-lookup"><span data-stu-id="44b60-220">Duration</span></span>|<span data-ttu-id="44b60-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-221">win:Double</span></span>|<span data-ttu-id="44b60-222">收集这些统计信息的时间量（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="44b60-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="44b60-223">吞吐量</span><span class="sxs-lookup"><span data-stu-id="44b60-223">Throughput</span></span>|<span data-ttu-id="44b60-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-224">win:Double</span></span>|<span data-ttu-id="44b60-225">在此间隔期间每秒完成的平均数量。</span><span class="sxs-lookup"><span data-stu-id="44b60-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="44b60-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="44b60-226">ThreadWave</span></span>|<span data-ttu-id="44b60-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-227">win:Double</span></span>|<span data-ttu-id="44b60-228">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="44b60-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="44b60-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="44b60-229">ThroughputWave</span></span>|<span data-ttu-id="44b60-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-230">win:Double</span></span>|<span data-ttu-id="44b60-231">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="44b60-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="44b60-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="44b60-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="44b60-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-233">win:Double</span></span>|<span data-ttu-id="44b60-234">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="44b60-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="44b60-235">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="44b60-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="44b60-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-236">win:Double</span></span>|<span data-ttu-id="44b60-237">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="44b60-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="44b60-238">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="44b60-238">ThroughputRatio</span></span>|<span data-ttu-id="44b60-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-239">win:Double</span></span>|<span data-ttu-id="44b60-240">在此间隔期间因活动工作线程计数变化导致的相对吞吐量变化。</span><span class="sxs-lookup"><span data-stu-id="44b60-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="44b60-241">Confidence</span><span class="sxs-lookup"><span data-stu-id="44b60-241">Confidence</span></span>|<span data-ttu-id="44b60-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-242">win:Double</span></span>|<span data-ttu-id="44b60-243">ThroughputRatio 字段的有效性测量。</span><span class="sxs-lookup"><span data-stu-id="44b60-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="44b60-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="44b60-244">NewcontrolSetting</span></span>|<span data-ttu-id="44b60-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="44b60-245">win:Double</span></span>|<span data-ttu-id="44b60-246">将作为活动线程计数未来变化基线的活动工作线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="44b60-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="44b60-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="44b60-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-248">Win:UInt16</span></span>|<span data-ttu-id="44b60-249">活动线程计数的未来变化量值。</span><span class="sxs-lookup"><span data-stu-id="44b60-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="44b60-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="44b60-250">ClrInstanceID</span></span>|<span data-ttu-id="44b60-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-251">Win:UInt16</span></span>|<span data-ttu-id="44b60-252">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44b60-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="44b60-253">I/O 线程事件</span><span class="sxs-lookup"><span data-stu-id="44b60-253">I/O Thread Events</span></span>  
 <span data-ttu-id="44b60-254">这些线程池事件针对 I/O 线程池（完成端口）中的线程发生，该过程是异步的。</span><span class="sxs-lookup"><span data-stu-id="44b60-254">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="44b60-255">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="44b60-255">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="44b60-256">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="44b60-256">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="44b60-257">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="44b60-257">Keyword for raising the event</span></span>|<span data-ttu-id="44b60-258">层次</span><span class="sxs-lookup"><span data-stu-id="44b60-258">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="44b60-259">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="44b60-259">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="44b60-260">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="44b60-260">Informational (4)</span></span>|  
  
 <span data-ttu-id="44b60-261">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-261">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="44b60-262">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-262">Event</span></span>|<span data-ttu-id="44b60-263">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b60-263">Event ID</span></span>|<span data-ttu-id="44b60-264">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="44b60-264">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="44b60-265">44</span><span class="sxs-lookup"><span data-stu-id="44b60-265">44</span></span>|<span data-ttu-id="44b60-266">在线程池中创建 I/O 线程。</span><span class="sxs-lookup"><span data-stu-id="44b60-266">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="44b60-267">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-267">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="44b60-268">字段名</span><span class="sxs-lookup"><span data-stu-id="44b60-268">Field name</span></span>|<span data-ttu-id="44b60-269">数据类型</span><span class="sxs-lookup"><span data-stu-id="44b60-269">Data type</span></span>|<span data-ttu-id="44b60-270">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-270">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="44b60-271">计数</span><span class="sxs-lookup"><span data-stu-id="44b60-271">Count</span></span>|<span data-ttu-id="44b60-272">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="44b60-272">win:UInt64</span></span>|<span data-ttu-id="44b60-273">I/O 线程数，包括新创建的线程。</span><span class="sxs-lookup"><span data-stu-id="44b60-273">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="44b60-274">NumRetired</span><span class="sxs-lookup"><span data-stu-id="44b60-274">NumRetired</span></span>|<span data-ttu-id="44b60-275">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="44b60-275">win:UInt64</span></span>|<span data-ttu-id="44b60-276">已停用的工作线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-276">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="44b60-277">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="44b60-277">ClrInstanceID</span></span>|<span data-ttu-id="44b60-278">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-278">Win:UInt16</span></span>|<span data-ttu-id="44b60-279">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44b60-279">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="44b60-280">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="44b60-280">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="44b60-281">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="44b60-281">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="44b60-282">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="44b60-282">Keyword for raising the event</span></span>|<span data-ttu-id="44b60-283">层次</span><span class="sxs-lookup"><span data-stu-id="44b60-283">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="44b60-284">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="44b60-284">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="44b60-285">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="44b60-285">Informational (4)</span></span>|  
  
 <span data-ttu-id="44b60-286">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-286">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="44b60-287">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-287">Event</span></span>|<span data-ttu-id="44b60-288">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b60-288">Event ID</span></span>|<span data-ttu-id="44b60-289">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="44b60-289">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="44b60-290">46</span><span class="sxs-lookup"><span data-stu-id="44b60-290">46</span></span>|<span data-ttu-id="44b60-291">I/O 线程变为停用候选项。</span><span class="sxs-lookup"><span data-stu-id="44b60-291">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="44b60-292">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-292">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="44b60-293">字段名</span><span class="sxs-lookup"><span data-stu-id="44b60-293">Field name</span></span>|<span data-ttu-id="44b60-294">数据类型</span><span class="sxs-lookup"><span data-stu-id="44b60-294">Data type</span></span>|<span data-ttu-id="44b60-295">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-295">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="44b60-296">计数</span><span class="sxs-lookup"><span data-stu-id="44b60-296">Count</span></span>|<span data-ttu-id="44b60-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="44b60-297">win:UInt64</span></span>|<span data-ttu-id="44b60-298">线程池中剩余的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-298">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="44b60-299">NumRetired</span><span class="sxs-lookup"><span data-stu-id="44b60-299">NumRetired</span></span>|<span data-ttu-id="44b60-300">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="44b60-300">win:UInt64</span></span>|<span data-ttu-id="44b60-301">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-301">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="44b60-302">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="44b60-302">ClrInstanceID</span></span>|<span data-ttu-id="44b60-303">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-303">Win:UInt16</span></span>|<span data-ttu-id="44b60-304">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44b60-304">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="44b60-305">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="44b60-305">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="44b60-306">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="44b60-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="44b60-307">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="44b60-307">Keyword for raising the event</span></span>|<span data-ttu-id="44b60-308">层次</span><span class="sxs-lookup"><span data-stu-id="44b60-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="44b60-309">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="44b60-309">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="44b60-310">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="44b60-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="44b60-311">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="44b60-312">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-312">Event</span></span>|<span data-ttu-id="44b60-313">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b60-313">Event ID</span></span>|<span data-ttu-id="44b60-314">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="44b60-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="44b60-315">47</span><span class="sxs-lookup"><span data-stu-id="44b60-315">47</span></span>|<span data-ttu-id="44b60-316">I/O 线程因在该线程变为停用候选项后的等待期间内达到 I/O 而恢复使用。</span><span class="sxs-lookup"><span data-stu-id="44b60-316">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="44b60-317">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-317">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="44b60-318">字段名</span><span class="sxs-lookup"><span data-stu-id="44b60-318">Field name</span></span>|<span data-ttu-id="44b60-319">数据类型</span><span class="sxs-lookup"><span data-stu-id="44b60-319">Data type</span></span>|<span data-ttu-id="44b60-320">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-320">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="44b60-321">计数</span><span class="sxs-lookup"><span data-stu-id="44b60-321">Count</span></span>|<span data-ttu-id="44b60-322">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="44b60-322">win:UInt64</span></span>|<span data-ttu-id="44b60-323">线程池中的 I/O 线程数，包括这一个。</span><span class="sxs-lookup"><span data-stu-id="44b60-323">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="44b60-324">NumRetired</span><span class="sxs-lookup"><span data-stu-id="44b60-324">NumRetired</span></span>|<span data-ttu-id="44b60-325">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="44b60-325">win:UInt64</span></span>|<span data-ttu-id="44b60-326">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-326">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="44b60-327">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="44b60-327">ClrInstanceID</span></span>|<span data-ttu-id="44b60-328">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-328">Win:UInt16</span></span>|<span data-ttu-id="44b60-329">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44b60-329">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="44b60-330">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="44b60-330">IOThreadTerminate</span></span>  
 <span data-ttu-id="44b60-331">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="44b60-331">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="44b60-332">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="44b60-332">Keyword for raising the event</span></span>|<span data-ttu-id="44b60-333">层次</span><span class="sxs-lookup"><span data-stu-id="44b60-333">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="44b60-334">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="44b60-334">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="44b60-335">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="44b60-335">Informational (4)</span></span>|  
  
 <span data-ttu-id="44b60-336">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-336">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="44b60-337">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-337">Event</span></span>|<span data-ttu-id="44b60-338">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b60-338">Event ID</span></span>|<span data-ttu-id="44b60-339">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="44b60-339">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="44b60-340">45</span><span class="sxs-lookup"><span data-stu-id="44b60-340">45</span></span>|<span data-ttu-id="44b60-341">在线程池中创建 I/O 线程。</span><span class="sxs-lookup"><span data-stu-id="44b60-341">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="44b60-342">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="44b60-342">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="44b60-343">字段名</span><span class="sxs-lookup"><span data-stu-id="44b60-343">Field name</span></span>|<span data-ttu-id="44b60-344">数据类型</span><span class="sxs-lookup"><span data-stu-id="44b60-344">Data type</span></span>|<span data-ttu-id="44b60-345">描述</span><span class="sxs-lookup"><span data-stu-id="44b60-345">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="44b60-346">计数</span><span class="sxs-lookup"><span data-stu-id="44b60-346">Count</span></span>|<span data-ttu-id="44b60-347">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="44b60-347">win:UInt64</span></span>|<span data-ttu-id="44b60-348">线程池中剩余的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-348">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="44b60-349">NumRetired</span><span class="sxs-lookup"><span data-stu-id="44b60-349">NumRetired</span></span>|<span data-ttu-id="44b60-350">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="44b60-350">win:UInt64</span></span>|<span data-ttu-id="44b60-351">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="44b60-351">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="44b60-352">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="44b60-352">ClrInstanceID</span></span>|<span data-ttu-id="44b60-353">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="44b60-353">Win:UInt16</span></span>|<span data-ttu-id="44b60-354">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44b60-354">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44b60-355">请参阅</span><span class="sxs-lookup"><span data-stu-id="44b60-355">See also</span></span>

- [<span data-ttu-id="44b60-356">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="44b60-356">CLR ETW Events</span></span>](clr-etw-events.md)

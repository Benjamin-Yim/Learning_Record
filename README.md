# Learning_Record
学习记录



# 2022年11月20日
这次解决了 OS3 的问题，历经一个礼拜，颇有波折。首先在 `TaskControlBlock` 中使用 [u32:MAX_SYSCALL_NUM] 运行测试，项目直接卡死亦或者太慢反正没有等到 Hello World 的下一句，索性直接改为 Vec、&'static [u32:MAX_SYSCALL_NUM]、RefCell 等方式。百般尝试后选择 Vec 来解决，顺便查询了一下 `lazy_static!` 的语义。然后是第二个问题 info.time 的问题。只能说审题很重要。最后的问题就是，删除了被抢占的时候，虽然想法是对的但是题目上写的清清楚楚：`运行时间 time 返回系统调用时刻距离任务第一次被调度时刻的时长，也就是说这个时长可能包含该任务被其他任务抢占后的等待重新调度的时间。` but 没仔细看所以应该很容易解决的问题，但是会过不去 case 测试。所以理解需求很重要，理解别人的语义很重要。虽然走了弯路但是也学了其他不少的知识点。

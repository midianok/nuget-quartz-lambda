# Quartz.Lambda
Quartz extension which allows to schedule jobs with lambda syntax.

Usage example
```c#
scheduler.ScheduleJob(() => Console.WriteLine("With TriggerBuilder"), 
    builder => builder.StartNow()
    .WithSimpleSchedule(x => x
        .WithIntervalInSeconds(10)
        .RepeatForever()));

scheduler.ScheduleJob(() => Console.WriteLine("With int delay and interval"), 0, 10);

scheduler.ScheduleJob(() => Console.WriteLine("And also with TimeSpan"), TimeSpan.FromSeconds(0), TimeSpan.FromSeconds(10));
```
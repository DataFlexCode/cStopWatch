# cStopWatch class
Provides a set of methods and properties that you can use to accurately measure elapsed time, with micro-seconds precision

## Remarks
A `Stopwatch` instance can measure elapsed time for one interval, or the total of elapsed time across multiple intervals. In a typical Stopwatch scenario, you call the `Start` method, then eventually call the `Stop` method, and then you check elapsed time using the `Elapsed` property.

A Stopwatch instance is either running or stopped; use `IsRunning` to determine the current state of a Stopwatch. Use `Start` to begin measuring elapsed time; use `Stop` to stop measuring elapsed time. Query the elapsed time value through the properties `Elapsed`, `ElapsedMilliSeconds`, `ElapsedMicroSeconds` or `ElapsedTicks`. You can query the elapsed time properties while the instance is running or stopped. The elapsed time properties steadily increase while the Stopwatch is running; they remain constant when the instance is stopped.

By default, the elapsed time value of a Stopwatch instance equals the total of all measured time intervals. Each call to `Start` begins counting at the cumulative elapsed time; each call to `Stop` ends the current interval measurement and freezes the cumulative elapsed time value. Use the `Reset` method to clear the cumulative elapsed time in an existing Stopwatch instance.

The Stopwatch measures elapsed time by counting timer ticks in the underlying timer mechanism. Use the `Frequency` and `IsHighResolution` fields to determine the precision and resolution of the Stopwatch timing implementation.

The Stopwatch class assists the manipulation of timing-related performance counters in your application.

## Example

```
Handle hoSW
Timespan tsRoutineTime 
BigInt  biRoutine_ms

Get Create (RefClass(cStopWatch)) to hoSW 

Send Start of hoSW
Send DoSomething 
Send Stop of hoSW 

Get Elapsed of hoSW to tsRoutineTime 
Get ElapsedMilliSeconds of hoSW to biRoutine_ms

```
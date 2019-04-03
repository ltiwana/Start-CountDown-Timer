# Start-CountDown-Timer
How often do you use <a href="https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-6" rel="noopener nofollow" target="_blank"><i>Start-Sleep</i></a> or <a href="https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-6" rel="noopener nofollow" target="_blank"><em>Sleep</em></a> in your <a href="https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6" rel="noopener nofollow" target="_blank">PowerShell</a> scripts? As you might have noticed, the default <a href="https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-6" rel="noopener nofollow" target="_blank"><em>Sleep</em></a> command in <a href="https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6" rel="noopener nofollow" target="_blank">PowerShell</a> is not very visual. Although, it's suitable for small pauses when you are testing something BUT if  you want to use a long pause, then it would be ideal to be able to see the time remaining before the script would move on to the next step.

I was recently testing something where I wanted to repeat the code execution after 5 minutes. Initially, I used the default <a href="https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-6" rel="noopener nofollow" target="_blank"><em>Sleep</em></a> command and ran my code. After some time, I would go back to <a href="https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6" rel="noopener nofollow" target="_blank">PowerShell</a> window to check the execution status, but I wouldn't know if it was executing a command, if it was sleeping or was just frozen. 

I wanted to make sure that f the script was at <a href="https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-6" rel="noopener nofollow" target="_blank"><em>Sleep</em></a>  command,  it should show how far along it was. So, I thought of creating a <a href="https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6" rel="noopener nofollow" target="_blank">PowerShell</a> function (`Start-CountDownTimer`) that could accept values in hours, minutes or seconds and show me a countdown timer.

This function is available on GitHub for download. All you need to do is import the function and specify a time in seconds, minutes or hours.

## Sample Runs:
### Example 1: 

By default, timer is set to 1 minute. So if you just run it without specifying anything, it will run a countdown for a minute.
![ScreenShot1](/Screenshots/1.png)

### Example 2:

You can not leave a parameter empty or pass anything other than numeric format. Use, for example, "`Start-CountDownTimer -Hours 1`" to start a count down for 1 hour.

![ScreenShot2](/Screenshots/2.png)
### Example 4:

In this example, I am counting down from 10 minutes.

`Start-CountDownTimer -Minutes 10`

![ScreenShot3](/Screenshots/3.png)
### Example 5:

Counting down from 100 seconds (1 Minute 40 Seconds).

`Start-CountDownTimer -Seconds 100`

![ScreenShot4](/Screenshots/4.png)
### Example 6:

You can also be very specific down to a second. The function will add all the provided parameters and start the countdown.

`Start-CountDownTimer -Hours 1 -Minutes 19 -Seconds 45`

![ScreenShot5](/Screenshots/5.png)
> OR
You can also do something like this:

`Start-CountDownTimer -Hours 1.5`

![ScreenShot6](/Screenshots/6.png)
Example 7:

If you don't specify parameter names like -Hours, - Minutes,  -Seconds, then, by default, first value is considered Seconds, second value is Minutes and third is Hours.

![ScreenShot7](/Screenshots/7.png)
![ScreenShot8](/Screenshots/8.png)

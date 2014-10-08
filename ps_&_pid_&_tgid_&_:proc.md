## ps & pid & tgid & /proc
ps 命令用来显示进程的名称 
默认包含了 #pid #tty #time #cmd
pid : 进程id
tty : ？
time: ?
cmd： ？

option select all process
-A  打印出来的还是这四列


/





### The difference between 'ps|wc -l'  'ps > ps.txt; wc -l ps.txt'

	//print processes include: bash、ps、wc and the head line
	//so the result will have four line
	ps | wc -l
	
	// result will have 3 three line
	//ps > ps.txt just have two processes bash & ps and the head line
	//PID TTY TIME COMMAND
	ps > ps.txt; wc -l ps.txt
	
### ip command



### /proc
	
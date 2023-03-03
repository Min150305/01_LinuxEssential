Linux Essentail 과정 정리


제 01장. Linux Command

제 02장. Directory Administration



<SORT 명령어>
cmd | sort
cmd | sort -r
cmd | sort -nr  -> 많이 사용하는 형식 

ps -ef | head | sort -k 2 -> 2번째 필드를 중심으로 정렬 
ps -ef | head | sort -k 2 -n -> 2번째 필드를 중심으로 정렬 / -n : 숫자가 적힌 필드니까 추가 옵션 
ps -ef | head | sort -k 3 -nr -> 3번째 필드를 중심으로 정렬  / -r :거꾸로 정렬

! sort = 출력결과 O / 여러 필드 O 있는경우 사용 

[실무예]파일/파일시스템 사용량 점검 
[root@server1 /test]# du -sk /var /etc   
768920	/var
32412	/etc

[root@server1 /var]# du -sk * -> 현재폴더 전체 사용량 보여줌 

[root@server1 /var]# du -sk * | sort -r     
541928	cache
4	tmp
216280	lib
12	spool
10688	log
 -> 출력이 숫자이기때문에 한글자씩 비교되어서 원하는값으로 표출이안됨 -> -n옵션을 추가해줘야한다
    5 > 4 > 2 > 1 한글자씩 비교해서 보여주기때문에 
	

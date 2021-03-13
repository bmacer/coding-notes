find operating system

        cat /etc/os-release
get current logged in user

        whoami
possible way to see users

        cat /etc/password
see environment variables

        env
see what i (user) can run as root

        sudo -l
compare two files for differences

        diff file1.txt file2.txt
split lines

        cut -d "." -f 1 file.txt
find unique lines

        sort -u
count unique lines

        uniq -c
delete all of a certain character ("t")

        tr -d "t"
see open ports

        ss -tl
another way to see open ports

        netstat -naote
investigate open server information

        nmap 127.0.0.1 -p 1234 -sV -sC
get parent process id of a process

        ps -o ppid= 21875
view current crontab

        crontab -l
edit current crontab

        crontab -e
find all files of a certain name while trashing permission errors

        find / 2>/dev/null | grep evil
searching files for a string inside file (recursively) while trashing errors

        grep abcDEF -R /var/* 2>/dev/null
shift letters

        echo "hello" | tr '[a-z]' '[n-za-m]' | tr '[A-Z]' '[N-ZA-M]'
search files including filename (-n):

        grep -n hello -R /tmp 2>/dev/null 
see cron options (files/folders)

        cat /etc/cron*
find folders/files with non-root permissions

        find /etc -not -group root -user root 2>/dev/null

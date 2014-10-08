Something deserve HEHE

grep 'Invalid' /var/log/auth.log | grep -v 'Failed' | awk '{print $8, $10}' > invalid


cut -d ' ' -f 1 invalid| sort | uniq -c|sort -n -r|head 10

cut -d 指定分隔符 -f 指定分割的区域
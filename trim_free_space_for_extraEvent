#!/bin/bash
# mounted storage:
_storage=/media/hdd
#left space in MB:
_wish_free_size=1000
#days to delete:
_maxdays=30

_free_size=$(df -m | grep $_storage | awk '{print $4}')

if (( $(echo "$_free_size < $_wish_free_size" |bc -l) )); then
        find $_storage/extraEvent/ -type f -mtime +$_maxdays -delete
else
        echo "free space left: $_free_size"
fi

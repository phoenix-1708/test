#!/bin/bash


cd /tmp

com () 
{ 
    tar --use-compress-program="pigz -k -$2 " -cf $1.tar.gz $1
}

time com ccache 1

cd /tmp
time rclone copy /tmp/rom/out/target/product/tissot/*.zip remote:tissot -P
cd /tmp/rom/out/target/product/tissot/
curl -s "https://api.telegram.org/bot${token_telegram}/sendmessage" --data "text=Download Link -> https://withered-lab-e844.harikumar1708.workers.dev/tissot/$(ls *.zip)=${id_telegram}&parse_mode=html"
cd /tmp
time rclone copy ccache.tar.gz remote:ccache/ci2 -P

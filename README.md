# monotonic_datetime
Primitive script to guarantee monotonic date/time between boots of RTC-less linux system

Includes one script that writes current date and time into files on shutdown, 
and another one that reads them out on startup. This guarantees at least sequential timestamp
on files being collected by Linux systems without realtime clock (like Jetson nano). Scripts are 
executed via dedicated service (that is valuable itself) that is launched by systemctl. 

Place the files into desired locations, then 
chown +x on_s*
and
systemctl enable start_and_stop.service

Command line used to find this crash:

../TriforceAFL/afl-fuzz -t 800000+ -i ../TriforceAFL/inputs -o ../TriforceAFL/outputs -QQ -- ../TriforceAFL/qemu_mode/qemu/mipsel-softmmu/qemu-system-mipsel -monitor telnet:127.0.0.1:4444,server -m 256 -M malta -kernel ../firmadyne_dev/vmlinux_3.2.1_mipsel -drive if=ide,format=raw,file=/home/zyw/experiment/firmadyne//scratch//2//image.raw -append root=/dev/sda1 console=ttyS0 nandsim.parts=64,64,64,64,64,64,64,64,64,64 rdinit=/firmadyne/preInit.sh rw debug ignore_loglevel print-fatal-signals=1 user_debug=31 firmadyne.syscall=0 -nographic -net nic,vlan=0 -net socket,vlan=0,listen=:2000 -net nic,vlan=1 -net socket,vlan=1,listen=:2001 -net nic,vlan=0 -net tap,vlan=0,id=net0,ifname=tap2_0,script=no -net nic,vlan=3 -net socket,vlan=3,listen=:2003 -aflFile @@

If you can't reproduce a bug outside of afl-fuzz, be sure to set the same
memory limit. The limit used for this fuzzing session was 2.00 GB.

Need a tool to minimize test cases before investigating the crashes or sending
them to a vendor? Check out the afl-tmin that comes with the fuzzer!

Found any cool bugs in open-source tools using afl-fuzz? If yes, please drop
me a mail at <lcamtuf@coredump.cx> once the issues are fixed - I'd love to
add your finds to the gallery at:

  http://lcamtuf.coredump.cx/afl/

Thanks :-)

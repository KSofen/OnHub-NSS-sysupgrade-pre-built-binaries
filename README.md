Google's OnHub routers stopped being supported by Google and the developers of OpenWrt stepped in.  Both the Asus and TP-Link versions of the router are supported.
However, OpenWrt did not support some of the advanced hardware present in the OnHub and still doesn't.  Specifically, the NSS support to offload much of the
computational burden enabling routers to perform tasks such as packet classification, anomaly detection, and traffic optimization more efficiently.
Qualcomm has been incorporating NNS into their router chips to enhance their capabilities and provide better performance.

That's when @ACwifidude stepped in along with @KONG and @vochong and patched OpenWrt source code to enable these chips and increase the speed and performance of the router.
I had never compiled code before and asked for somoene to share a pre-built binary, but was told it was bad form to ask for so much work and time on the OpenWrt forum.

So I set about learning how to do it myself and I was finally able to successfully compile a binary after a dozen failed attempts.  It doesn't take much to spoil a project.
In my case it often came down to typographical errors the original programmers made which took a lot of time to find and correct.  @vochong walked me through creating a
diffconfig so I could compile a version of OpenWrt with just the basics, but which could be added on to easily with packages that didn't require any kmod drivers.  But, 
even he made a few typographical errors I had to find and correct the hard way.  My compiling machine was a Raspberry Pi 4, so every attempt took a long time.
When enabling the NSS hardware, it was necessary to customize all the kmod drivers and so you can't upgrade any of them from regular OpenWrt sources.

The OnHub routers are dated and there is faster and better hardware out there.  @ACwifidude and @Kong have moved on to better hardware and their NSS code will no longer
compile for the OnHub.  What I have here is what I consider, the last, best version of firmware for the OnHub routers.  They perform at the top limit of the hardware's
capability.  OpenWrt developers say they won't support NSS in the future due to the major differences in the kmod packages required.  Standard OpenWrt will max out at about
half the Internet speed the router is capable of, but will be supported and this may change in the future.  It's a difficult process to even get third party firmware
to load on the OnHub router - it has to be put in developer mode by disassembling it a bit and finding the hidden button and pressing it at just the right moment in the
boot process.  But that process is explained in another wiki and it works.

So, try this at your own risk if you want to extend the life of your OnHub router.  I can't support it or update it anymore.  Anytime you flash a router you risk bricking it.
This particular firmware is a good one to start out with and if you screw up your setup, reflashing this will clean the slate and let you start over from scratch easily.

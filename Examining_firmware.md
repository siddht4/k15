# file

US_AC10UV2.0re_V16.03.16.12_multi_TDE01.bin

#for model

AC10U

#supports

AC10V3

# binwalk #1

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
10328         0x2858          LZMA compressed data, properties: 0x5D, dictionary size: 8388608 bytes, uncompressed size: 7776024 bytes


# extracting #1

command : binwalk -e file.bin


# binwalk #2

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
1047616       0xFFC40         MySQL MISAM index file Version 8
5406736       0x528010        Linux kernel version 3.10.9
5607216       0x558F30        SHA256 hash constants, little endian
6268820       0x5FA794        Unix path: /lib/firmware/updates/3.10.90
6330902       0x609A16        Neighborly text, "neighbor channel_load:==> after adjust channel scores:"
6488956       0x63037C        Neighborly text, "NeighborSolicitsPv6: %s: can't add protocol"
6488976       0x630390        Neighborly text, "NeighborAdvertisementsrotocol"
6493634       0x6315C2        Neighborly text, "neighbor %.2x%.2x.%pM lost rename link %s to %s"
6645248       0x656600        CRC32 polynomial table, little endian
6773712       0x675BD0        AES S-Box
6812945       0x67F511        Intel x86 or x64 microcode, sig 0x0205080d, pf_mask 0x14191e21, 1B1E-12-17, rev 0x1f000000, size 1
6812961       0x67F521        Intel x86 or x64 microcode, sig 0x0305090e, pf_mask 0x161c2225, 1E21-14-19, rev 0x22000000, size 1
6813281       0x67F661        Intel x86 or x64 microcode, sig 0x0205080d, pf_mask 0x14191e21, 1B1E-12-17, rev 0x1f000000, size 1
6813297       0x67F671        Intel x86 or x64 microcode, sig 0x0305090e, pf_mask 0x161c2225, 1E21-14-19, rev 0x22000000, size 1

# Extracting #2 
#in parts

command : dd if=2858.bin of=1.bin bs=1 skip=$(printf "%d" 0xFFC40) count=1047616
 
 




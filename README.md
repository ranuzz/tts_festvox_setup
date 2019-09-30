# TTS

http://www.festvox.org/festival/index.html

## installation
http://www.festvox.org/docs/manual-2.4.0/festival_6.html#Installation

## site setting

vim festival/lib/siteinit.scm

add (set! voice_default 'voice_cmu_indic_hin_ab_cg)

## text2wave command

 bin/text2wave /mnt/d/projects/data/hindi_test.txt -o /mnt/d/projects/data/hindi_test.wav  
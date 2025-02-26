to fix Z fighting on the hud and visible hud in widescreen hacked emulator, do the following

in ark/ghui/hud_panel.dta, at the top, create a new define
#define Z_FIXER
(
   {score_num_frame.mesh set_local_pos 0 -1 42}
   {score_mult_2.mesh set_local_pos 17.9 -2 -39.6}
   {score_mult_3.mesh set_local_pos -17.4 -2 -39.6}
   {score_num_6.mesh set_local_pos 60 -3 41}
   {score_num_5.mesh set_local_pos 37 -3 41}
   {score_num_4.mesh set_local_pos 14 -3 41}
   {score_num_3.mesh set_local_pos -16 -3 41}
   {score_num_2.mesh set_local_pos -38 -3 41}
   {score_num_1.mesh set_local_pos -61 -3 41}
)

call this define in both (intro_start) and (intro_skip)
simply make a new line under `{$this reset}` and put `Z_FIXER`



To fix the visible hud on slide in:
`{hud set_showing FALSE}` in (intro_start)
and
`{hud set_showing TRUE}` in (slide_meter_in)

included is a vanilla file with these additions and comments if you need help
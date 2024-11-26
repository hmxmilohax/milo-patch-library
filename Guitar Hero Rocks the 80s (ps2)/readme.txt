This is not an exec patch but is a file patch in a milo.
This fixes the 'X' on the combo multiplier in game

to use, extract your gh2 or 80s ark
place streak_overlay.milo_ps2 at /hud/gen/streak_overlay.milo_ps2 in your ark and rebuild



alternatively, for a script only fix, create a new func as such

{func
   fix_streak_meter_emu
   ;check if we are loaded in the affected hud's
   {if {|| {== {gamecfg get hud_file} hud_sp.milo} {== {gamecfg get hud_file} hud_practice.milo}}
      ;find and move the mesh slightly
      ;original value in the milo is -17.5 -0.96 -39.64
      {{{{hud loaded_dir} find BandStreakDisplay1} find score_mult_3.mesh} set_local_pos -18.5 -0.96 -39.64}
   }
}

then, in the (enter) block of hud, call it

{fix_streak_meter_emu}
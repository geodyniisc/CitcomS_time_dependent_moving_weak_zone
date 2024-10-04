# CitcomS_time_dependent_moving_weak_zone
This CitcomS version is used to introduce moving material layer using ggrd handling. The original code can was made to handle moving material layer, however needs to be turned on in GGrd_handling.c.

#### This code is modified to assimilate time-dependent-material file
#### The previous version had this turned off.

For turning the functionality append Ggrd_handling.c
###################################################################
ifdef GGRD_NN_BACKWARD_COMPATIBLE

  use_nearneighbor = FALSE;
  
#else

  /* no interpolation */
  
  use_nearneighbor = TRUE;
  
#endif

  if(E->control.ggrd_mat_is_code)
  
    use_nearneighbor = TRUE;
    
    
E->control.ggrd.time_hist.nvtimes=140; ###################### for turning it on

  /*
     if we have not initialized the time history structure, do it now
     
  */
  
  if(!E->control.ggrd.time_hist.init){
  
  ##################################################

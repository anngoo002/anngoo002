
REPORT z00_prog7.
TYPES: BEGIN OF ty_tab, 
points TYPE i,
END OF ty_tab.
DATA: gt_tab TYPE STANDARD TABLE OF ty_ tab.
DATA: gs_tab TYPE ty_ tab.
DATA: gv_total TYPE i ,
gy_tmp TYPE i .
gv_tmp = 15.

DO 4 TIMES.
Gs_tab-points = gv_ tmp.
APPEND gs_ tab TO gt_tab.
gv_tmp = gv_tmp +1.
ENDDO.

LOOP AT gt_tab INTO gs_tab.
If sy-tabix <> 3.
EXIT.
ELSE.
CONTINUE .
ENDIF.
gv_total = gv_total + gs_tab-points.
ENDLOOP.
gv_total = gv_total + gv_tmp.
WRITE g_total.

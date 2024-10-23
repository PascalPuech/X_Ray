PERMITTED BY APPLICABLE LAW. EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE PROGRAM IS WITH YOU. SHOULD THE PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF ALL NECESSARY SERVICING, REPAIR OR CORRECTION.

12. IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MAY MODIFY AND/OR REDISTRIBUTE THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT NOT LIMITED TO LOSS OF DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD PARTIES OR A FAILURE OF THE PROGRAM TO OPERATE WITH ANY OTHER PROGRAMS), EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.

END OF TERMS AND CONDITIONS

In this Matlab program, the fminsearch function is more efficient than on Octave.
Moreover, in case of Octave, you need to compile the lectura.c file in mex function or change in 
readfile.m and readfileagain.m the line:
[x,y]=lectura(nom);
by:
x=load(nom);y=x(:,2);x=x(:,1);

To interface corresponds to the Main_Carbon_XRay.m file
In Matlab, execute it.

The X-ray diffractogram should be acquired with a Cu anode, and in the applied correction, only the multiwavelength correction has to be considered, not the background as removing the background fails for 2D materials.
The file is a two columns, the first column is 2theta and the second the X-ray intensity.

The procedure is:
1/ "read": select the file (you have an exemple 2000.txt)
2/ "remove bg" (bg for background)
For the fitting, if some other bands are here, you can use "from" and "to" with "Supp"
3/ "20-33" give you Lc
Then, you can zoom on the 40-60 2theta range (top left), (+)
4/ remove from=50 to to=56 and press "Suppr"
5/ clic on "35-70" with only turbo for turbostratic stacking
6/ add "pair" and clic again on "35-70", then you've got the fitting and the fraction of each component
unzoom with (-) (top-left) and then zoom on the 70-90 range
7/ remove from=82 to to=88 and press "Suppr"
8/ clic on "70-85"

You can "save" (see in the directory the new files) 
The area "0.0" and "-" is to translate the data (usefull if really noisy or with too negative values)
With this fitting, you only consider 10(0) and 11(0), not 112, it will be done in a near future.

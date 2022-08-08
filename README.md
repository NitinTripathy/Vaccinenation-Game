# Vaccinenation-Game
Interplay between cost and benefits triggers nontrivial vaccination uptake
c = .;
\[Beta] = .;
\[Alpha] = .;
T = .;
\[Gamma] = .;
f[y_] := -y*(1 - 
     y)*(c - (\[Beta]*\[Alpha]*
        T*(1 - \[Gamma]))*(1 - ((1 - \[Gamma])*y)));
sol = Solve[f[y] == 0, y]

c = 0.1;
\[Beta] = 0.55;
\[Alpha] = 0.3;
T = 1;
\[Gamma] = 0.1;
f[y_] := -y*(1 - 
     y)*(c - (\[Beta]*\[Alpha]*
        T*(1 - \[Gamma]))*(1 - ((1 - \[Gamma])*y)));
Plot[ f[y], {y, 0, 1}, PlotStyle -> {Blue, Dashed}, Frame -> True, 
 FrameLabel -> {"y", "dy/dt"}, 
 FrameStyle -> Directive[Black, Thick, 14], Filling -> Axis, 
 FillingStyle -> LightBlue]
 
 c = 0;
\[Beta] = 0.55;
\[Alpha] = 0.3;
T = 1;
\[Gamma] = 0.1;
f[y_] := -y*(1 - 
     y)*(c - (\[Beta]*\[Alpha]*
        T*(1 - \[Gamma]))*(1 - ((1 - \[Gamma])*y)));
Plot[ f[y], {y, 0, 1}, PlotStyle -> {Red, Dashed}, Frame -> True, 
 FrameLabel -> {"y", "dy/dt"}, 
 FrameStyle -> Directive[Black, Thick, 14], Filling -> Axis, 
 FillingStyle -> LightBlue]
 
 \[Beta] =.;
c = 0.1;
\[Alpha] = 0.4;
T = 1;
f = (c/T);
h = Which[\[Beta] <= (f/\[Alpha]), 
   0, (f/\[Alpha]) < \[Beta] < (2*(f/\[Alpha])), (1 - (f/(\[Beta]*\
\[Alpha]))), (2*(f/\[Alpha])) <= \[Beta], ((\[Beta]*\[Alpha])/(4*f))];
PiecewiseExpand[h]
Plot[h, {\[Beta], 0, 1}, PlotStyle -> {Black}, Frame -> True, 
 FrameLabel -> {"\[Beta]", "y*(max)"}, 
 FrameStyle -> Directive[Black, Thick, 14], Filling -> Axis, 
 FillingStyle -> Yellow]
 
 \[Beta] = 0.45;
c = 0.1;
\[Alpha] = 0.4;
T = 1;
\[Gamma] = 0.1;
\[Mu] = 0.2;
f = (c/T);
z = (1 - \[Gamma]);
i[\[Gamma]_] := ((1/(1 - \[Gamma]))*(1 - (c/(\[Beta]*
         T*\[Alpha]*(1 - \[Gamma])))))
a = Plot[ i[\[Gamma]], {\[Gamma], 0, 1}, PlotRange -> {0, 1}, 
  PlotStyle -> {Blue}, Axes -> False, AxesOrigin -> {-0, 0}, 
  Frame -> True, FrameLabel -> {"\[Gamma]", "y*"}, 
  FrameStyle -> Directive[Black, Thick, 14], GridLines -> Automatic, 
  PlotLegends -> "Expressions"]
\[Beta] = 0.85;
c = 0.1;
\[Alpha] = 0.4;
T = 1;
\[Gamma] = 0.1;
\[Mu] = 0.2;
f = (c/T);
z = (1 - \[Gamma]);
i[\[Gamma]_] := ((1/(1 - \[Gamma]))*(1 - (c/(\[Beta]*
         T*\[Alpha]*(1 - \[Gamma])))))
b = Plot[ i[\[Gamma]], {\[Gamma], 0, 1}, PlotRange -> {0, 1}, 
  PlotStyle -> {Red}, Axes -> False, AxesOrigin -> {-0, 0}, 
  Frame -> True, FrameLabel -> {"\[Gamma]", "y*"}, 
  FrameStyle -> Directive[Black, Thick, 14], GridLines -> Automatic, 
  PlotLegends -> "Expressions"]
Show[a, b]

\[Beta] =.;
c = 0.1;
\[Alpha] = .;
T = 1;
\[Gamma] = 0.1;
\[Mu] = 0.2;
f = (c/T);
z = (1 - \[Gamma]);
i[\[Alpha]_, \[Beta]_] := ((1/(1 - \[Gamma]))*(1 - (c/(\[Beta]*
         T*\[Alpha]*(1 - \[Gamma])))))
plot1 = DensityPlot[
   i[\[Alpha], \[Beta]], {\[Alpha], 0, 1}, {\[Beta], 0, 1}, 
   ColorFunction -> "Rainbow", PlotPoints -> 40, Axes -> False, 
   AxesOrigin -> {-0, 0}, Frame -> True, 
   FrameLabel -> {"\[Beta]", "\[Alpha]"}, 
   FrameStyle -> Directive[Black, Thick, 14]];
plot2 = ContourPlot[
   i[\[Alpha], \[Beta]] == 0, {\[Alpha], 0, 1}, {\[Beta], 0, 1}, 
      ContourStyle -> {Thick, White}, PlotPoints -> 40];
Show[plot1, plot2]

\[Beta] =.;
c = 0.1;
\[Alpha] = 0.4;
T = 1;
\[Gamma] = 0.4;
\[Mu] = 0.1;
f = (c/T);
z = (1 - \[Gamma]);
r = 1;
k = 0;
i[\[Beta]_] := ((1/(1 - \[Gamma]))*(1 - (c/(\[Beta]*
          T*\[Alpha]*(1 - \[Gamma])))));
a1 = Plot[i[\[Beta]], {\[Beta], 0, 1}, PlotRange -> {0, 1}, 
  PlotStyle -> {Blue}]
\[Beta] =.;
c = 0.05;
\[Alpha] = 0.4;
T = 1;
\[Gamma] = 0.4;
\[Mu] = 0.1;
f = (c/T);
z = (1 - \[Gamma]);
r = 1;
k = 0;
i[\[Beta]_] := ((1/(1 - \[Gamma]))*(1 - (c/(\[Beta]*
          T*\[Alpha]*(1 - \[Gamma])))));
a2 = Plot[i[\[Beta]], {\[Beta], 0, 1}, PlotRange -> {0, 1}, 
  ColorFunction -> "Rainbow"]
Show[a1, a2]

Link: https://au.mathworks.com/matlabcentral/fileexchange/23629-export_fig

Github: https://github.com/lamngoctam/export_fig


**Locating Ghostscript/pdftops** - You may find a dialogue box appears when using export_fig, asking you to locate either [Ghostscript](http://www.ghostscript.com) or [pdftops (part of the Xpdf package)](http://www.xpdfreader.com). These are separate applications which export_fig requires to perform certain functions. If such a dialogue appears it is because export_fig can't find the application automatically. This is because you either haven't installed it, or it isn't in the normal place. Make sure you install the applications correctly first. They can be downloaded from the following places:  
 1. Ghostscript:     [www.ghostscript.com](http://www.ghostscript.com)
 2. pdftops (install the Xpdf package): [www.xpdfreader.com](http://www.xpdfreader.com)

If you choose to install them in a non-default location then point export_fig to this location using the dialogue box.

**Image quality** - when publishing images of your results, you want them to look as good as possible. By default, when outputting to lossy file formats (PDF, EPS and JPEG), export_fig uses a high quality setting, i.e. low compression, for images, so little information is lost. This is in contrast to MATLAB's print and saveas functions, whose default quality settings are poor. For example:
```Matlab
A = im2double(imread('peppers.png'));
B = randn(ceil(size(A, 1)/6), ceil(size(A, 2)/6), 3) * 0.1;
B = cat(3, kron(B(:,:,1), ones(6)), kron(B(:,:,2), ones(6)), kron(B(:,:,3), ones(6)));
B = A + B(1:size(A, 1),1:size(A, 2),:);
imshow(B);
print -dpdf test.pdf
```
generates a PDF file, a sub-window of which looks (when zoomed in) like this:

![](https://farm6.staticflickr.com/5613/15405290309_881b2774d6_o_d.png)

while the command

```Matlab
export_fig test.pdf
```
on the same figure produces this:

![](https://farm4.staticflickr.com/3947/14971168174_687473133f_o_d.png)

While much better, the image still contains some compression artifacts (see the low level noise around the edge of the pepper). You may prefer to export with no artifacts at all, i.e. lossless compression. Alternatively, you might need a smaller file, and be willing to accept more compression. Either way, export_fig has an option that can suit your needs: `-q<val>`, where <val> is a number from 0-100, will set the level of lossy image compression (again in PDF, EPS and JPEG outputs only; other formats are lossless), from high compression (0) to low compression/high quality (100). If you want lossless compression in any of those formats then specify a <val> greater than 100. For example:
```Matlab
export_fig test.pdf -q101
```
again on the same figure, produces this:

![](https://farm6.staticflickr.com/5608/15405803908_934512c1fe_o_d.png)

Notice that all the noise has gone.

**Example code in Matlab - LaTex**
```
- run simulation in Matlab-
  export_fig test.pdf
```

```
\usepackage{pdfpages}
....
\newpage
\begin{center}
\begin{figure}[ht]
  \includegraphics[page=1,width=.5\textwidth]{image/test.pdf}
  \includegraphics[page=1,width=.5\textwidth]{image/test.pdf}
  \caption{Test}
  \label{fig:Test}
\end{figure}
\end{center}
```

**Change size of xticks in Matlab plot** 
link: https://au.mathworks.com/matlabcentral/answers/321518-subplot-change-size-of-xtick-ytick
```
set(gca, 'XTick', 0.5:0.1:1, 'YTick', 0:0.2:1);
set(gca, 'FontSize', 18)
axis(gca,'square');
legend('3DOP', 'MCG-D', 'MCG', 'EB', 'SS', 'BING');
xlabel('Intersection Over Union','Fontsize',12);
ylabel('Recall','Fontsize',12);
```

**Best view in Matlab plot** 
```
%%
ax = gca;
ax.GridColor = [0, 0, 0];
ax.LineWidth =1;
view([-20,-45,110]);
% axis(gca,'square');
%%
zlim([-0.5 3]);
% ylim([0 10.5]);

%%
% set(gca, 'XTick', 0.5:0.1:10, 'YTick', 0:0.2:6);
set(gca, 'FontSize', 20)
% axis(gca,'square');
% legend('3DOP', 'MCG-D', 'MCG', 'EB', 'SS', 'BING');
% xlabel('Intersection Over Union','Fontsize',12);
% ylabel('Recall','Fontsize',12);
```

web link
----------

::

    \href{https://github.com/hsrmbeamertheme/hsrmbeamertheme}{\textsc{hsrm} Beamer}

    \begin{center}
      \url{github.com/matze/mtheme}
    \end{center}

source code
-------------------

\begin{verbatim}    
  \documentclass{beamer}
  \usetheme{m}
\end{verbatim}

\emph{Fira Sans} 

add image
----------------

    \begin{figure} 
        \centering 
        \includegraphics[trim={0 8.5cm 0 8.5cm},clip, scale=0.6]{./img/car_network.pdf} \caption{Autonomous vehicles for platooning} 
        \label{fig:platoon} 
    \end{figure}

    \begin{figure}[h]
        \centering
        \includegraphics[trim={0 0 0 0},clip,scale=0.5]{./img/objectives.png} \caption{Objectives of this research}
        \label{fig:objectives}
    \end{figure}
    
font size
--------------
::

  {\small
  \begin{itemize}
      \item Security of future vehicle applications (e.g., electric cars, ITS)
      \item Security for other transport systems (e.g., railways, aerospace)
  \end{itemize}
  }

https://en.wikibooks.org/wiki/LaTeX/Fonts

::

    \tiny 
    \scriptsize 
    \footnotesize
    \small 
    \normalsize 
    \large 
    \Large 
    \LARGE 
    \huge 	
    \Huge


multi column lists
-----------------------

::

    \begin{frame}{Lists}
      \begin{columns}[T,onlytextwidth]
        \column{0.33\textwidth}
          Items
          \begin{itemize}
            \item Milk \item Eggs \item Potatos
          \end{itemize}

        \column{0.33\textwidth}
          Enumerations
          \begin{enumerate}
            \item First, \item Second and \item Last.
          \end{enumerate}

        \column{0.33\textwidth}
          Descriptions
          \begin{description}
            \item[PowerPoint] Meeh. \item[Beamer] Yeeeha.
          \end{description}
      \end{columns}
    \end{frame}


Animation
----------

::

    \begin{frame}{Animation}
      \begin{itemize}[<+- | alert@+>]
        \item \alert<4>{This is\only<4>{ really} important}
        \item Now this
        \item And now this
      \end{itemize}
    \end{frame}


tikzpicture
---------------

::

    \begin{frame}{Figures}
      \begin{figure}
        \newcounter{density}
        \setcounter{density}{20}
        \begin{tikzpicture}
          \def\couleur{alerted text.fg}
          \path[coordinate] (0,0)  coordinate(A)
                      ++( 90:5cm) coordinate(B)
                      ++(0:5cm) coordinate(C)
                      ++(-90:5cm) coordinate(D);
          \draw[fill=\couleur!\thedensity] (A) -- (B) -- (C) --(D) -- cycle;
          \foreach \x in {1,...,40}{%
              \pgfmathsetcounter{density}{\thedensity+20}
              \setcounter{density}{\thedensity}
              \path[coordinate] coordinate(X) at (A){};
              \path[coordinate] (A) -- (B) coordinate[pos=.10](A)
                                  -- (C) coordinate[pos=.10](B)
                                  -- (D) coordinate[pos=.10](C)
                                  -- (X) coordinate[pos=.10](D);
              \draw[fill=\couleur!\thedensity] (A)--(B)--(C)-- (D) -- cycle;
          }
        \end{tikzpicture}
        \caption{Rotated square from
        \href{http://www.texample.net/tikz/examples/rotated-polygons/}{texample.net}.}
      \end{figure}
    \end{frame}

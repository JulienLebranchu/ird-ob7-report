LaTeX style files for IRD-OB7 reports.
===============================================

Basic usage:
------------

The basic structure of a deliverable formatted according with these
styles should be (minimally):

    \documentclass[11pt]{report}
    \usepackage{ird-ob7}  
    
    \begin{document}
    
    %% a Changelog. Each call to \istChange adds an entry to the
    %% changelog. After LaTeX is run, it will generate a table on page 2
    %% containing all changes. N.B.: I could not find a way to generate
    %% this table directly, so the whiledo{} loop in istprog.sty writes
    %% the changelog table to a temp file (more or less the way tables of
    %% content are generated), so you have to run LaTeX twice to update
    %% this table (as you would to update the TOC).
    \istChange{dd/mm/yyyy}{v1.o}{Name (Partner short name)}{Draft report template}
    \istChange{...}{}{...}{}
    \istChange{}{}{}{}

  % Project Meta Information
\ProjectFullTitle{Report title}
\ProjectAcronym{Acronyme}
\ProjectRefNo{Reference}

% reporter Number and Title (according to DoA)
\reportName{[Title as appears in the DoA]}

% DOI Number (will be provided by the coordinator)
\doiNumber{} % leave empty if no DOI Number is provided


\reportAuthor{Author}
\reportFPAuthor{}


% report Short Title
\reportShortTile{Short title}

% report Version, Contractual and Actual Date, Dissemination Level, Type
\reportVersion{v1.0}
\ActualDate{\today}
\reportDissLevel{CO} % PU, PP, RE, CO

% Provision of Keywords (about 5-10)
\reportKeywords{[List of free keywords relevant to the report]}

\reportType{Rapport}

% report Status
\reportStatus{d} %% d = draft, f = final, s = submitted
    
    \makecover
    % page 3: table of contents
    \newpage
    \fancypagestyle{plain}{}
    
    \settableofcontents
    \tableofcontents
    
    \vfill
    \section*{List of abbreviations}
    
    \begin{tabular}[h]{ll}
     EC	        &	European Commission \\
     DoA	&	Description of Action\\
    \end{tabular}
    
    
    \newpage
    \section{Your first section}
    
    \subsection{A subsection of your first section}
    
    etc
    
    \bibliography{your-bib-file}
    \bibliographystyle{apacite} %% recommended 
    \{document}

Further details
---------------

See template.tex/template.pdf in this directory.

If you have any thoughts on how to improve this style, feel free to
implement them and share your results. The same goes for bug fixes.

Just clone the project and 'Have fun!'
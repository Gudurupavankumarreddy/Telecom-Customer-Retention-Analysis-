%-------------------------
% ATS-Friendly Resume – G Pavan Kumar Reddy
% Compiler: XeLaTeX or pdfLaTeX
%-------------------------
\documentclass[letterpaper,10.5pt]{article}

\usepackage{latexsym}
\usepackage[empty]{fullpage}
\usepackage{titlesec}
\usepackage{marvosym}
\usepackage[usenames,dvipsnames]{color}
\usepackage{verbatim}
\usepackage{enumitem}
\usepackage[hidelinks]{hyperref}
\usepackage{fancyhdr}
\usepackage[english]{babel}
\usepackage{tabularx}
\usepackage{multicol}
\input{glyphtounicode}

\pagestyle{fancy}
\fancyhf{}
\fancyfoot{}
\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{0pt}

% Margins
\addtolength{\oddsidemargin}{-0.5in}
\addtolength{\evensidemargin}{-0.5in}
\addtolength{\textwidth}{1in}
\addtolength{\topmargin}{-.5in}
\addtolength{\textheight}{1.0in}

\urlstyle{same}
\raggedbottom
\raggedright
\setlength{\tabcolsep}{0in}

% Section formatting
\titleformat{\section}{
  \vspace{-6pt}\scshape\raggedright\large
}{}{0em}{}[\color{black}\titlerule \vspace{-4pt}]

\pdfgentounicode=1

%-------------------------
% Custom commands
\newcommand{\resumeItem}[1]{
  \item\small{#1 \vspace{-1.5pt}}
}

\newcommand{\resumeSubheading}[4]{
  \vspace{-1pt}\item
    \begin{tabular*}{0.97\textwidth}[t]{l@{\extracolsep{\fill}}r}
      \textbf{#1} & #2 \\
      \textit{\small#3} & \textit{\small #4} \\
    \end{tabular*}\vspace{-5pt}
}

\newcommand{\resumeProjectHeading}[2]{
    \item
    \begin{tabular*}{0.97\textwidth}{l@{\extracolsep{\fill}}r}
      \small#1 & #2 \\
    \end{tabular*}\vspace{-5pt}
}

\newcommand{\resumeSubHeadingListStart}{\begin{itemize}[leftmargin=0.1in, label={}]}
\newcommand{\resumeSubHeadingListEnd}{\end{itemize}}
\newcommand{\resumeItemListStart}{\begin{itemize}[leftmargin=0.2in]}
\newcommand{\resumeItemListEnd}{\end{itemize}\vspace{-3pt}}

%-------------------------------------------
\begin{document}

%---------- HEADING ----------
\begin{center}
  {\LARGE \textbf{G Pavan Kumar Reddy}} \\[4pt]
  \small
  +91-7569357689 $\,\cdot\,$
  \href{mailto:gudurupavanpavankumarreddy@gmail.com}{gudurupavanpavankumarreddy@gmail.com} $\,\cdot\,$
  Kurnool, India $\,\cdot\,$
  \href{https://linkedin.com/in/YOUR-PROFILE}{LinkedIn} $\,\cdot\,$
  \href{https://github.com/YOUR-GITHUB}{GitHub} $\,\cdot\,$
  \href{https://YOUR-PORTFOLIO}{Portfolio}
\end{center}

%---------- SUMMARY ----------
\section{Summary}
B.Tech graduate in AI \& ML with hands-on experience in SQL, Python, Power BI, and Excel. Proven ability to deliver end-to-end data analytics projects — from data cleaning and exploratory data analysis to interactive dashboards and machine learning models. Seeking an entry-level Data Analyst role to turn raw data into actionable business insights.

%---------- SKILLS ----------
\section{Technical Skills}
\resumeSubHeadingListStart
  \item{
    \textbf{Languages \& Querying:} Python, SQL (MySQL, SQL Server), DAX \\
    \textbf{Libraries:} Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn, SciPy \\
    \textbf{Visualization \& BI:} Power BI, Excel (pivot tables, VLOOKUP, data validation) \\
    \textbf{Analytics:} Exploratory Data Analysis, Feature Engineering, Statistical Analysis, KPI Reporting, Business Intelligence, Machine Learning \\
    \textbf{Other:} Google Sheets, CRM data management, Data Cleaning, Window Functions, CTEs
  }
\resumeSubHeadingListEnd

%---------- EXPERIENCE ----------
\section{Work Experience}
\resumeSubHeadingListStart

  \resumeSubheading
    {Data Analyst Intern}{Mar 2026 -- Present}
    {RupeeVyze Financial Services}{Remote}
    \resumeItemListStart
      \resumeItem{Standardized and cleaned \textbf{88,000+ lead records} across 6 Indian states in Excel/Google Sheets, enforcing a fixed schema (Name, Mobile, Email, City, State) and resolving duplicates, missing values, invalid emails, and formatting inconsistencies.}
      \resumeItem{Migrated validated datasets into the company CRM, maintaining data integrity and ensuring accurate records for the sales and outreach pipeline.}
    \resumeItemListEnd

\resumeSubHeadingListEnd

%---------- PROJECTS ----------
\section{Projects}
\resumeSubHeadingListStart

  \resumeProjectHeading
    {\textbf{Walmart Sales Analysis} $|$ \emph{Python, MySQL, Power BI, Pandas, SciPy}}{20 Days}
    \resumeItemListStart
      \resumeItem{Performed end-to-end analysis on \textbf{\$6.73B in sales} across 45 stores (2010--2012) using Python, MySQL, and Power BI.}
      \resumeItem{Identified November as the peak holiday month with a \textbf{42\% sales lift} vs. non-holiday weeks; flagged high-risk stores using unemployment and sales thresholds.}
      \resumeItem{Built a \textbf{3-page interactive Power BI dashboard} (Executive Overview, Seasonality \& Holiday Analysis, Economic Impact) using SQL window functions, CTEs, and YoY growth KPIs.}
    \resumeItemListEnd

  \resumeProjectHeading
    {\textbf{Telecom Customer Churn Analysis} $|$ \emph{Python, Scikit-Learn, Pandas, Matplotlib}}{31 Days}
    \resumeItemListStart
      \resumeItem{Analyzed \textbf{7,043 customer records} to identify churn drivers; discovered month-to-month contracts churn at \textbf{42.7\%} vs. 11.3\% for annual contracts.}
      \resumeItem{Built a \textbf{Random Forest model} to score customers on a 0--100 risk scale and flagged the first 6 months as a critical churn window (52.9\% churn rate).}
      \resumeItem{Quantified annual revenue impact and designed \textbf{5 targeted retention strategies} with projected ROI to support business decision-making.}
    \resumeItemListEnd

  \resumeProjectHeading
    {\textbf{Pizza Sales Analysis} $|$ \emph{MySQL, Power BI, DAX}}{1 Month}
    \resumeItemListStart
      \resumeItem{Analyzed \textbf{49,574 pizzas sold} across 21,350 orders, generating \$817K+ in revenue; identified Fridays and July as peak sales periods.}
      \resumeItem{Built a 2-page Power BI dashboard and used SQL CTEs, CASE statements, and aggregations to surface KPIs; recommended upselling and seasonal promotion strategies.}
    \resumeItemListEnd

\resumeSubHeadingListEnd

%---------- EDUCATION ----------
\section{Education}
\resumeSubHeadingListStart
  \resumeSubheading
    {Parul University}{Vadodara, India}
    {B.Tech in Artificial Intelligence and Machine Learning}{2021 -- 2025}
\resumeSubHeadingListEnd

%---------- CERTIFICATIONS ----------
\section{Certifications}
\resumeSubHeadingListStart
  \item{\small
    Databases and SQL for Data Science \textit{(IBM / Coursera)} \quad $\cdot$ \quad
    Data Science with AI \quad $\cdot$ \quad
    Data Analytics Job Simulation \textit{(Accenture / Forage)}
  }
\resumeSubHeadingListEnd

%-------------------------------------------
\end{document}

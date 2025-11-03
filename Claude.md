# Building a LaTeX Resume

This guide will help you create a professional resume using LaTeX.

## Prerequisites

- LaTeX distribution installed (TeX Live, MiKTeX, or MacTeX)
- Text editor (VS Code, TeXShop, Overleaf, etc.)
- Basic understanding of LaTeX syntax

## Quick Start

### 1. Basic Resume Template

Create a file named `resume.tex` with the following structure:

```latex
\documentclass[11pt,a4paper]{article}

% Packages
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{geometry}
\usepackage{enumitem}
\usepackage{hyperref}

% Page setup
\geometry{
    left=1in,
    right=1in,
    top=1in,
    bottom=1in
}

% Remove page numbers
\pagestyle{empty}

% Customize hyperlinks
\hypersetup{
    colorlinks=true,
    linkcolor=blue,
    urlcolor=blue
}

\begin{document}

% Header
\begin{center}
    {\LARGE \textbf{Your Name}}\\[0.5em]
    \href{mailto:your.email@example.com}{your.email@example.com} |
    (123) 456-7890 |
    \href{https://linkedin.com/in/yourprofile}{LinkedIn} |
    \href{https://github.com/yourusername}{GitHub}
\end{center}

\vspace{1em}

% Education
\section*{Education}
\noindent
\textbf{University Name} \hfill City, State\\
\textit{Degree, Major} \hfill Month Year -- Month Year
\begin{itemize}[leftmargin=1.5em, itemsep=0.2em]
    \item GPA: X.XX/4.0
    \item Relevant Coursework: Course 1, Course 2, Course 3
\end{itemize}

% Experience
\section*{Experience}
\noindent
\textbf{Company Name} \hfill City, State\\
\textit{Job Title} \hfill Month Year -- Present
\begin{itemize}[leftmargin=1.5em, itemsep=0.2em]
    \item Achievement or responsibility with quantifiable impact
    \item Another achievement highlighting technical skills
    \item Third point demonstrating leadership or results
\end{itemize}

% Projects
\section*{Projects}
\noindent
\textbf{Project Name} | \textit{Technologies Used} \hfill Month Year\\
\begin{itemize}[leftmargin=1.5em, itemsep=0.2em]
    \item Brief description of what the project does
    \item Technical challenges overcome or key features implemented
\end{itemize}

% Skills
\section*{Technical Skills}
\begin{itemize}[leftmargin=1.5em, itemsep=0.2em]
    \item \textbf{Languages:} Python, JavaScript, Java, C++
    \item \textbf{Frameworks:} React, Node.js, Django, Flask
    \item \textbf{Tools:} Git, Docker, AWS, SQL
\end{itemize}

\end{document}
```

### 2. Compiling Your Resume

**Command Line:**
```bash
pdflatex resume.tex
```

**VS Code:**
Install the LaTeX Workshop extension and use the build command (Ctrl+Alt+B or Cmd+Option+B).

**Overleaf:**
Upload the .tex file and it will compile automatically.

## Popular Resume Classes

### moderncv

A popular package for modern-looking resumes:

```latex
\documentclass[11pt,a4paper,sans]{moderncv}
\moderncvstyle{classic}
\moderncvcolor{blue}

\usepackage[scale=0.75]{geometry}

\name{First}{Last}
\title{Resumé title}
\address{street}{city}{country}
\phone[mobile]{+1~(234)~567~890}
\email{email@example.com}
\social[linkedin]{john.doe}
\social[github]{johndoe}

\begin{document}
\makecvtitle

\section{Education}
\cventry{2011--2015}{Degree}{Institution}{City}{\textit{Grade}}{Description}

\section{Experience}
\cventry{2015--Present}{Job Title}{Employer}{City}{}{Description}

\end{document}
```

Install with: `tlmgr install moderncv` or use Overleaf.

### altacv

A modern, column-based resume template:

```latex
\documentclass[10pt,a4paper,ragged2e,withhyper]{altacv}

\geometry{left=1.25cm,right=1.25cm,top=1.5cm,bottom=1.5cm,columnsep=1.2cm}

\usepackage{paracol}

\name{Your Name}
\tagline{Your Position or Tagline}
\personalinfo{
    \email{email@example.com}
    \phone{000-00-0000}
    \location{City, Country}
    \linkedin{username}
    \github{username}
}

\begin{document}
\makecvheader

\columnratio{0.6}
\begin{paracol}{2}

% Left column
\cvsection{Experience}

\cvevent{Job Title}{Company}{Month 20XX -- Present}{Location}
\begin{itemize}
    \item Achievement
    \item Achievement
\end{itemize}

\switchcolumn

% Right column
\cvsection{Skills}
\cvtag{Python}
\cvtag{JavaScript}

\end{paracol}

\end{document}
```

## Best Practices

### Content

1. **Keep it concise**: One page for early career, two pages maximum for experienced professionals
2. **Use action verbs**: Led, developed, implemented, designed, optimized
3. **Quantify achievements**: "Increased performance by 40%" rather than "Made it faster"
4. **Tailor to the job**: Highlight relevant experience and skills
5. **Use reverse chronological order**: Most recent experience first

### Formatting

1. **Consistent spacing**: Use `\vspace{}` for vertical spacing
2. **Font size**: 10-12pt for body text, larger for name
3. **Margins**: 0.5-1 inch on all sides
4. **Line spacing**: Use `\setlength{\parskip}{}` to control spacing
5. **Bullet points**: Use `enumitem` package for customization

### LaTeX Tips

1. **Comments**: Use `%` for notes that won't appear in the PDF
2. **Non-breaking spaces**: Use `~` to prevent line breaks (e.g., `Dr.~Smith`)
3. **Em-dashes**: Use `---` for professional punctuation
4. **Special characters**: Escape with `\` (e.g., `\&`, `\%`, `\$`)

## Useful Packages

```latex
\usepackage{enumitem}      % Customize lists
\usepackage{hyperref}      % Clickable links
\usepackage{fontawesome5}  % Icons for contact info
\usepackage{xcolor}        % Colors
\usepackage{tabularx}      % Better tables
\usepackage{multicol}      % Multiple columns
```

## Example: Adding Icons

```latex
\usepackage{fontawesome5}

\href{mailto:email@example.com}{\faEnvelope\ email@example.com}
\href{https://github.com/user}{\faGithub\ user}
\href{https://linkedin.com/in/user}{\faLinkedin\ user}
\faPhone\ (123) 456-7890
```

## Customization

### Custom Section Formatting

```latex
% Define custom section command
\newcommand{\mysection}[1]{
    \vspace{0.5em}
    \noindent\textbf{\large #1}
    \vspace{0.2em}
    \hrule
    \vspace{0.5em}
}

% Use it
\mysection{Experience}
```

### Two-Column Layout

```latex
\begin{tabularx}{\textwidth}{Xr}
    \textbf{Company Name} & City, State \\
    \textit{Job Title} & Month Year -- Present \\
\end{tabularx}
```

## Common Issues

### Issue: PDF not updating
**Solution**: Delete auxiliary files (.aux, .log, .out) and recompile

### Issue: Package not found
**Solution**: Install missing packages with `tlmgr install packagename`

### Issue: Overfull hbox warnings
**Solution**: Adjust margins or rephrase text to fit better

### Issue: Links not clickable
**Solution**: Ensure `hyperref` package is loaded and use `\href{url}{text}`

## Resources

- [Overleaf Resume Templates](https://www.overleaf.com/latex/templates/tagged/cv)
- [CTAN (Comprehensive TeX Archive Network)](https://ctan.org)
- [LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX)
- [LaTeX Stack Exchange](https://tex.stackexchange.com)

## Example Workflow

1. Start with a template or create basic structure
2. Fill in your information
3. Compile and review the PDF
4. Iterate on formatting and content
5. Get feedback from peers
6. Export to PDF for distribution
7. Keep .tex file in version control for easy updates

## Version Control

Keep your resume in Git:

```bash
git init
git add resume.tex
git commit -m "Initial resume version"
```

Create versions for different job applications:
```bash
git checkout -b software-engineer
# Modify resume for software engineering roles
git commit -am "Tailored for SWE positions"
```

## Exporting

Always share PDF, not the .tex file:
```bash
pdflatex resume.tex
# This creates resume.pdf
```

For online applications, ensure the PDF is:
- Not password protected
- Text-selectable (not scanned images)
- Under common size limits (typically 2-5 MB)

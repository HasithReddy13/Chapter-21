{\rtf1\ansi\ansicpg1252\cocoartf2868
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\froman\fcharset0 Times-Bold;\f1\froman\fcharset0 Times-BoldItalic;\f2\froman\fcharset0 Times-Roman;
\f3\froman\fcharset0 Times-Italic;\f4\fmodern\fcharset0 Courier;\f5\fnil\fcharset0 Menlo-Regular;
\f6\froman\fcharset0 TimesNewRomanPSMT;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;\red109\green109\blue109;}
{\*\expandedcolortbl;;\cssrgb\c0\c0\c0;\cssrgb\c50196\c50196\c50196;}
{\*\listtable{\list\listtemplateid1\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid1\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid1}
{\list\listtemplateid2\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid101\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid2}
{\list\listtemplateid3\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid201\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid3}}
{\*\listoverridetable{\listoverride\listid1\listoverridecount0\ls1}{\listoverride\listid2\listoverridecount0\ls2}{\listoverride\listid3\listoverridecount0\ls3}}
\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\deftab720
\pard\pardeftab720\sa321\partightenfactor0

\f0\b\fs48 \cf0 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Chapter 21: Knowledge Without Boundaries\
\pard\pardeftab720\sa298\partightenfactor0

\f1\i\fs36 \cf0 Enterprise Knowledge Management and Legal Research
\f0\i0 \
\pard\pardeftab720\sa280\partightenfactor0

\fs28 \cf0 Design of Agentic Systems with Case Studies\
\pard\pardeftab720\partightenfactor0

\f2\b0\fs24 \cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Core Claim\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 The knowledge retrieval bottleneck in enterprise AI is not search quality but chunking strategy. How documents are segmented determines whether an agent retrieves contextually coherent information or semantically fragmented noise. The choice of chunking strategy is not a preprocessing detail \'97 it is the primary architectural decision in any knowledge-intensive agentic system.\
The metric you would trust to tell you the system is working \'97 retrieval confidence \'97 is the metric that hides the failure.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 The Architectural Argument\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 This chapter demonstrates the book's master argument \'97 
\f3\i architecture is the leverage point, not the model
\f2\i0  \'97 at the retrieval layer:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\partightenfactor0
\ls1\ilvl0\cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 A frontier embedding model retrieving structurally incoherent chunks produces 
\f0\b 0.20 context adherence
\f2\b0 \
\ls1\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 The same embedding model retrieving agentic chunks produces 
\f0\b 0.60 context adherence
\f2\b0 \
\ls1\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 The model did not change. The chunk boundaries did.\
\ls1\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Every component in the pipeline performed correctly. The failure was locked in before any of them ran.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Repository Structure\
\pard\pardeftab720\partightenfactor0

\f4\b0\fs26 \cf0 chapter21_knowledge_without_boundaries/\

\f5 \uc0\u9500 \u9472 \u9472 
\f4  notebooks/\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9500 \u9472 \u9472 
\f4  00_setup.ipynb              # Environment setup and verification\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9500 \u9472 \u9472 
\f4  01_corpus_preparation.ipynb # 10 court opinions, corpus analysis\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9500 \u9472 \u9472 
\f4  02_chunking_strategies.ipynb # Five strategies compared side by side\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9500 \u9472 \u9472 
\f4  03_failure_case.ipynb       # THE DELIBERATE FAILURE \'97 run this on camera\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9500 \u9472 \u9472 
\f4  04_evaluation.ipynb         # Chunk size sensitivity analysis\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9500 \u9472 \u9472 
\f4  05_defense.ipynb            # Routing layer closes the gap\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9500 \u9472 \u9472 
\f4  data/\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9492 \u9472 \u9472 
\f4  processed/\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9474 
\f4        
\f5 \uc0\u9492 \u9472 \u9472 
\f4  corpus.json         # 10 court opinions, 10 queries\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9500 \u9472 \u9472 
\f4  figures/                    # All generated figures\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9492 \u9472 \u9472 
\f4  results/                    # Experiment outputs (JSON)\

\f5 \uc0\u9500 \u9472 \u9472 
\f4  chapter/\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9492 \u9472 \u9472 
\f4  chapter_21_knowledge_without_boundaries.md  # Full chapter prose\

\f5 \uc0\u9500 \u9472 \u9472 
\f4  authors_note/\

\f5 \uc0\u9474 
\f4    
\f5 \uc0\u9492 \u9472 \u9472 
\f4  authors_note.md             # 3-page design, tool usage, self-assessment\

\f5 \uc0\u9492 \u9472 \u9472 
\f4  README.md\
\pard\pardeftab720\partightenfactor0

\f2\fs24 \cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Quick Start\
\pard\pardeftab720\sa280\partightenfactor0

\fs28 \cf0 1. Clone the repository\
\pard\pardeftab720\partightenfactor0

\f4\b0\fs26 \cf0 git clone https://github.com/[your-username]/chapter21-knowledge-without-boundaries\
cd chapter21-knowledge-without-boundaries\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 2. Create and activate a virtual environment\
\pard\pardeftab720\partightenfactor0

\f4\b0\fs26 \cf0 python3 -m venv venv\
source venv/bin/activate  # Mac/Linux\
# venv\\Scripts\\activate   # Windows\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 3. Install dependencies\
\pard\pardeftab720\partightenfactor0

\f4\b0\fs26 \cf0 pip install jupyter langchain langchain-community sentence-transformers \\\
            chromadb tiktoken matplotlib numpy nltk pandas seaborn ipykernel\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 4. Register the Jupyter kernel\
\pard\pardeftab720\partightenfactor0

\f4\b0\fs26 \cf0 python -m ipykernel install --user --name=chapter21 --display-name="Chapter 21 (venv)"\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 5. Launch Jupyter\
\pard\pardeftab720\partightenfactor0

\f4\b0\fs26 \cf0 jupyter notebook\
\pard\pardeftab720\sa240\partightenfactor0

\f0\b\fs24 \cf0 Select the "Chapter 21 (venv)" kernel for every notebook.
\f2\b0 \
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Running the Notebooks\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 Run in order. Each notebook depends on the previous one's output.\

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrt\brdrnil \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth3432\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth4172\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth3744\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0

\f0\b \cf0 Notebook\cell 
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0
\cf0 What it does\cell 
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0
\cf0 Expected output\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth3432\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth4172\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth3744\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f4\b0\fs26 \cf0 00_setup
\f2\fs24 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Installs dependencies, verifies environment\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f4\fs26 \cf0 Status: READY TO PROCEED
\f2\fs24 \cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth3432\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth4172\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth3744\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f4\fs26 \cf0 01_corpus_preparation
\f2\fs24 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Loads 10 court opinions, analyzes structure\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f4\fs26 \cf0 corpus.json
\f2\fs24  saved\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth3432\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth4172\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth3744\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f4\fs26 \cf0 02_chunking_strategies
\f2\fs24 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Implements all 5 strategies on Palsgraf\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Side-by-side comparison figure\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth3432\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth4172\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth3744\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f4\fs26 \cf0 03_failure_case
\f2\fs24 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f0\b \cf0 Triggers the deliberate failure
\f2\b0 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Inversion: 0.20 vs 0.60 adherence\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth3432\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth4172\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth3744\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f4\fs26 \cf0 04_evaluation
\f2\fs24 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Chunk size sensitivity (256/512/1024)\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Non-monotonic result\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrt\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth3432\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth4172\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth3744\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f4\fs26 \cf0 05_defense
\f2\fs24 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Routing layer closes the gap\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Routing matches agentic performance\cell \lastrow\row
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 The Deliberate Failure Case (Notebook 03)\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 This is the core demonstration. Run it in two phases:\
\pard\pardeftab720\sa240\partightenfactor0

\f0\b \cf0 Phase 1 \'97 Trigger the failure:
\f2\b0  Run cells 1\'966. Cell 6 will deliberately crash with a 
\f4\fs26 RuntimeError
\f2\fs24 :\
\pard\pardeftab720\partightenfactor0

\f4\fs26 \cf0 HUMAN DECISION NODE \'97 PIPELINE HALTED\
Complete the verification checklist before proceeding.\
\pard\pardeftab720\sa240\partightenfactor0

\f2\fs24 \cf0 This is correct behavior. Read the checklist, fill in the verification record, then change:\
\pard\pardeftab720\partightenfactor0

\f4\fs26 \cf0 HUMAN_DECISION_COMPLETE = False  # 
\f5 \uc0\u8594 
\f4  change to True\
\pard\pardeftab720\sa240\partightenfactor0

\f0\b\fs24 \cf0 Phase 2 \'97 Observe the inversion:
\f2\b0  Run cells 7\'9615. Cell 11 will print:\
\pard\pardeftab720\partightenfactor0

\f4\fs26 \cf0 Strategy A (Fixed-Size, 512 tokens):\
  Context Adherence: 0.20  
\f5 \uc0\u8592 
\f4  CORRECTNESS\
  Avg Similarity:    0.71  
\f5 \uc0\u8592 
\f4  CONFIDENCE\
\
Strategy B (Agentic):\
  Context Adherence: 0.60  
\f5 \uc0\u8592 
\f4  CORRECTNESS\
  Avg Similarity:    0.69  
\f5 \uc0\u8592 
\f4  CONFIDENCE\
\
High confidence is not a proxy for correct retrieval.\
The score is doing its job perfectly. That is the problem.\
\pard\pardeftab720\sa240\partightenfactor0

\f2\fs24 \cf0 Strategy A is more confident AND less correct than Strategy B. This is the architectural failure the chapter demonstrates.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Reproducing the Failure\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 The failure is reproducible from a fresh clone. The exact causal chain:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\partightenfactor0
\ls2\ilvl0\cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Court opinions have logical structure (Facts 
\f6 \uc0\u8594 
\f2  Reasoning 
\f6 \uc0\u8594 
\f2  Holding 
\f6 \uc0\u8594 
\f2  Dissent)\
\ls2\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Fixed-size chunking ignores this structure, cutting every 512 tokens\
\ls2\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	3	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 The embedding model encodes topic and vocabulary \'97 but not logical polarity\
\ls2\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	4	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 The dissent and the majority reasoning score nearly identical similarity to a holding query\
\ls2\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	5	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 The retrieval system returns the wrong chunk with high confidence\
\ls2\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	6	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 The LLM generates a faithful answer from wrong context\
\ls2\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	7	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 The answer is wrong. The model is blamed. Step 1 is not examined.\
\pard\pardeftab720\sa240\partightenfactor0

\f0\b \cf0 To trigger the failure yourself:
\f2\b0  Run notebook 03 with 
\f4\fs26 HUMAN_DECISION_COMPLETE = True
\f2\fs24  and observe Cell 11. Then run notebook 04 to confirm that no chunk size parameter closes the gap that strategy selection closes.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Key Results\

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrt\brdrnil \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth2399\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1975\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth1482\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0

\fs24 \cf0 Architecture\cell 
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0
\cf0 Context Adherence\cell 
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0
\cf0 Avg Similarity\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth2399\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1975\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth1482\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f2\b0 \cf0 Fixed-Size (512 tokens)\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 0.20\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 0.71\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth2399\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1975\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth1482\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Agentic Chunking\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 0.60\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 0.69\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrt\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth2399\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1975\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth1482\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Routing Layer (Defense)\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 0.60\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 0.69\cell \lastrow\row
\pard\pardeftab720\sa240\partightenfactor0

\f0\b \cf0 The inversion:
\f2\b0  Strategy A retrieves wrong material with more confidence than Strategy B retrieves correct material. High similarity score is not a proxy for correct retrieval.\

\f0\b The gap tuning cannot close:
\f2\b0  No chunk size (256, 512, or 1024 tokens) achieves the adherence that agentic chunking achieves. The averages cancel out. The failures don't.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 The Five Chunking Strategies\

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrt\brdrnil \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth1412\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1700\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth5725\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0

\fs24 \cf0 Strategy\cell 
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0
\cf0 Structure Aware\cell 
\pard\intbl\itap1\pardeftab720\qc\partightenfactor0
\cf0 Failure Signature\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth1412\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1700\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth5725\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0

\f2\b0 \cf0 Fixed-size\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 No\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Fragments logical units; high confidence on wrong material\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth1412\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1700\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth5725\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Sentence-level\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Partial\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Severs conditions from obligations\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth1412\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1700\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth5725\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Recursive\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Partial\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Honors paragraph breaks that fall mid-argument\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth1412\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1700\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth5725\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Semantic\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Yes (local)\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Misses gradual argument development\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrt\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth1412\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx2880
\clvertalc \clshdrawnil \clwWidth1700\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx5760
\clvertalc \clshdrawnil \clwWidth5725\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Agentic\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Yes (global)\cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf0 Non-reproducible across LLMs on unformatted documents\cell \lastrow\row
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Corpus\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 10 public-domain US federal court opinions on proximate cause in tort law, sourced from CourtListener. All opinions use explicit FACTS / REASONING / HOLDING / DISSENT section structure.\
Cases include: 
\f3\i Palsgraf v. Long Island Railroad Co.
\f2\i0  (1928), 
\f3\i Wagon Mound No. 1
\f2\i0  (1961), 
\f3\i Re Polemis
\f2\i0  (1921), 
\f3\i Donoghue v. Stevenson
\f2\i0  (1932), 
\f3\i Hughes v. Lord Advocate
\f2\i0  (1963), and five others.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Human Decision Node\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 The Human Decision Node in notebook 03 Cell 6 implements the mandatory checkpoint described in the chapter. It halts the pipeline and requires human verification of three conditions before agentic chunking is applied to the full corpus:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\partightenfactor0
\ls3\ilvl0\cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 All documents use consistent section headers\
\ls3\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 No additional document types require a routing layer\
\ls3\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	3	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 A 10% corpus sample has been verified manually\
\pard\pardeftab720\sa240\partightenfactor0
\cf0 This checkpoint exists because the cost of a wrong chunking decision compounds with every document indexed. The routing layer cannot be finalized by an AI scaffold \'97 it requires human judgment about corpus structure.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Note on Experimental Numbers\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 The demonstration corpus uses 10 opinions and a lightweight embedding model (
\f4\fs26 all-MiniLM-L6-v2
\f2\fs24 ) for reproducibility without API keys. The directional result \'97 fixed-size chunking produces higher confidence on incorrect retrievals than agentic chunking produces on correct ones \'97 holds across corpus sizes and embedding models.\
The chapter's stated values (0.41 vs 0.89 context adherence) reflect a larger corpus with a production embedding model. The experimental values here (0.20 vs 0.60) use stricter adherence scoring that requires explicit holding markers and zero dissent contamination \'97 producing a more conservative estimate.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 Author\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 Chapter 21 of 
\f3\i Design of Agentic Systems with Case Studies
\f2\i0  by Nik Bear Brown.\
\pard\pardeftab720\sa240\partightenfactor0

\f3\i \cf0 Architecture is the leverage point. The model is not.
\f2\i0 \
}
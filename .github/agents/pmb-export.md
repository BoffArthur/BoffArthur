# PMB memory export - arthur.boff

_Exported 2026-11-17 19:42 · 28 memories_

## activity (11)

- **2026-11-17 19:09** - Auditada a integração de RTK com os testes SGS: 25 módulos, 359 métodos de teste e 10.363 linhas; identificado que o hook global está ausente e que o comando unittest atual usa saída -v, impedindo filtragem eficaz.
  - _from: agent · importance 0.45_
- **2026-11-17 19:09** - Recomendado usar rtk test python -m unittest discover -s tests -p "test*.py" sem -v, mantendo teste por módulo para depuração, além de executar rtk init -g para ativar rewrites automáticos.
  - _from: agent · importance 0.48_
- **2026-11-17 19:14** - Configurado RTK por padrão no SGS: hook Copilot local em .github/hooks/rtk-rewrite.json, instruções locais em .github/copilot-instructions.md e hooks globais Copilot/Claude no usuário.
  - _from: agent · importance 0.40_
- **2026-11-17 19:14** - Padronizados os testes unittest em rtk test python -m unittest ... sem -v em AGENTS.md e documentação relacionada.
  - _from: agent · importance 0.51_
- **2026-11-17 19:14** - Validado tests.test_service_boundaries via RTK: 2 testes passaram em 0.001s.
  - _from: agent · importance 0.44_
- **2026-11-17 19:26** - Investigado o gráfico de raios GDeT: a segmentação global funde arcos consecutivos com raios diferentes; no caso PJT 2754, 11 arcos AFS viram 7 segmentos medidos e uma região R8/R40 é ajustada como R26,34, deslocando IDs e posições.
  - _from: agent · importance 0.40_
- **2026-11-17 19:26** - Plano de correção definido: usar subcontornos externos AFS como janelas espaciais alinhadas ao nominal, medir cada arco separadamente e manter segmentação genérica apenas como fallback explícito.
  - _from: agent · importance 0.40_
- **2026-11-17 19:28** - Corrigidas as margens Qt/Matplotlib dos gráficos 2D GDeT/Flor, restaurados os valores dos spinboxes laterais ao retirar NoButtons incompatível com o estilo e liberados pan/zoom permanentes no gráfico de raios; regressões específicas e tests.test_qt_shared passaram.
  - _from: agent · importance 0.40_
- **2026-11-17 19:30** - Reinvestigado com PJT3029.6_FEAs19r3: E2 físico em (7,31;64,74) é rotulado E13, enquanto E13 físico em (34,22;-0,13) é rotulado E2; os 10 arcos AFS viram 7, fundindo E6–E9 em um falso R27,64.
  - _from: agent · importance 0.40_
- **2026-11-17 19:30** - Atualizado o plano para usar PJT3029.6 como regressão principal: identidade por subcontorno físico AFS, não por sequência tipo/raio, eliminando a troca E2↔E13.
  - _from: agent · importance 0.40_
- **2026-11-17 19:32** - Plano ajustado por correção do usuário: o encaixe rígido global entre seção teórica e FEA Lines deve ocorrer antes da medição dos arcos; cada arco usa janela nominal fixa, sem alinhamento local que masque deslocamentos.
  - _from: agent · importance 0.40_

## fact (14)

- **2026-11-10 18:26** - PMB activated on 2026-11-10
  - _from: - · importance 0.70_
- **2026-11-10 19:30** ★lesson - SGS change rules: preserve all existing functional behavior unless explicitly requested; make incremental, scope-limited changes; no unrelated refactoring, renaming public interfaces, moving files, or replacing working components without a clear requirement.
  - _from: lesson · importance 0.85_
- **2026-11-10 19:30** ★lesson - SGS reuse and style: before creating new classes, functions, styles, or services, check for an existing implementation to reuse; follow the current architecture, naming conventions, theme system, and PySide6 component patterns.
  - _from: lesson · importance 0.86_
- **2026-11-10 19:30** ★lesson - SGS legacy restriction: the SGS_legacy folder (path defined as SGS_LEGACY_PATH in AGENTS.md) is read-only reference material. Consult it only when the user explicitly mentions the Legacy version; never modify or execute its files; do not copy complete legacy modules.
  - _from: lesson · importance 0.85_
- **2026-11-10 19:30** ★lesson - SGS reporting: report failures and data-dependent skips before completing a task.
  - _from: lesson · importance 0.85_
- **2026-11-10 19:30** ★lesson - SGS regression tests: run only when the user explicitly asks, from the project root with: python -m unittest discover -s tests -p "test*.py" -v. Never run the full test suite without the user's request. README.md mentions pytest, but AGENTS.md defines the unittest command.
  - _from: lesson · importance 0.89_
- **2026-11-10 19:30** - Special Geometry Studio (SGS) 6.0 Preview is a PySide6/Qt desktop app for engineering geometry. Entrypoint: qt_main.py. Processing is local with no external services. Dependencies: requirements.txt; install via requirements_install.bat.
  - _from: - · importance 0.85_
- **2026-11-10 19:30** - Special Geometry Studio (SGS) structure: qt_*.py are Qt UIs; *_core.py, *_services.py and sca_domain.py hold domain and services; api/ has native COPRA APIs and database analysis; assets/ has icons, themes and showcase; docs/ has technical docs; tests/ has tests; library_assets/ holds the geometry library (DXF/CSP2/DB).
  - _from: - · importance 0.80_
- **2026-11-10 19:30** - Special Geometry Studio (SGS) modules and status: SCA (Scan Contour Analysis, GOM ZEISS scans) Available; AFS (Advanced Forming Strategy) In validation; Geometry Library Available; Geometry Comparator Available; Projects and Files In evolution; Viabilities In evolution.
  - _from: - · importance 0.85_
- **2026-11-10 19:30** - Special Geometry Studio (SGS) purpose: integrated flow Organize, Analyze, Develop, Register, Reuse for measured contour analysis, forming strategy, geometry organization and feasibility studies. SCA views: Geometric Explorer, Statistical Explorer, Overview (RMS, MAE, extremes, tolerance, trend).
  - _from: - · importance 0.80_
- **2026-11-10 19:30** - Special Geometry Studio (SGS) AFS GD&T FEA Results: compares the simulated final outer contour (DXF) with a nominal library geometry. Profile tolerance total zone = 2 x max absolute deviation after best-fit alignment. Input is an Abaqus .inp (C3D4/C3D6/C3D8) with a default 100 mm end discard; coordinates assumed in mm; each 100 mm section is evaluated.
  - _from: - · importance 0.77_
- **2026-11-10 19:30** - Special Geometry Studio (SGS) privacy and distribution: internal use only (voestalpine Meincol); private repository with no public license; external distribution requires prior review and approval; scan data is published by GOM ZEISS on the internal network; screenshots show real environment data.
  - _from: - · importance 0.90_
- **2026-11-10 19:40** ★lesson - SGS UNC paths: file tools (view, glob) reject UNC paths (\\server\...). Use the drive letter mapped to the UNC share (Z: per AGENTS.md) if it exists; otherwise check mappings in the terminal (PowerShell: Get-PSDrive -PSProvider FileSystem, or net use) before reading network files.
  - _from: lesson · importance 0.86_
- **2026-11-17 19:28** ⚠failure - O módulo tests.test_qt_afs ainda falha em test_gdt_3d_initial_view_is_isometric_with_y_up, fora das alterações de 2D: câmera atual com up Z em vez de Y esperado.
  - _from: failure · importance 0.85_

## goal (3)

- **2026-11-13 11:49** - SGS GDeT 3D: free orbit button, XYZ axes toggle, XY-aligned initial view (qt_afs.py)
  - _from: - · importance 0.72_
- **2026-11-17 18:54** - Organizar gráficos e área de trabalho das subseções GDeT
  - _from: - · importance 0.75_
- **2026-11-17 19:21** - Corrigir margens dos gráficos 2D, visibilidade dos campos laterais e pan/zoom do gráfico de raios
  - _from: - · importance 0.73_

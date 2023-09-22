# Minicurso Hardware SIC2023

## Conteúdo do Curso

### Dia 1

+ Apresentação do Minicurso
	+ O que vamos estudar?
		+ Visão baixa: Interconexão, Transistores, Estruturas e Limitações de Circuitos
		+ Visão alta: Componentes (GPU, MOBO, CPU, etc) e como se relacionam
	+ Como vamos estudar?
		+ Prática: contato com o hardware em questão
		+ Teoria: estudo do hardware a partir de suas especificações e arquitetura
	+ Quais as limitações?
		+ Tempo 
	+ Quero saber mais...
		+ Leia os links adicionais providos neste arquivo
+ Módulo 1: Como computadores se comunicam
	+ Nível alto e Baixo
	+ Pacotes de Dados
	+ Tipos de Comunicação:
		+ Interna
			+ Barramento
			+ Ponto a Ponto
			+ UCIe
				+ [AnandTech](https://www.anandtech.com/show/17288/universal-chiplet-interconnect-express-ucie-announced-setting-standards-for-the-chiplet-ecosystem) 
		+ Externa
			+ USB
			+ Ethernet
			+ HDMI / VGA / Display Port / DVI
			+ P2
+ Módulo 2: Como computadores armazenam dados
	+ Armazenamento em disco e capacitor
+ Módulo 3: Como computadores processam
	+ Portas lógicas
	+ Ordenação dos circuitos dentro dos processadores
	+ Linguagens de descrição de hardware (HDL)
+ Módulo 4: Tipos de computadores e processadores
	+ Classes de computadores
		+ Dispositivos Móveis, Desktop, Server, Cluster, Internet das Coisas/Embarcados
	+ CPU, TPU, GPGPU, ASIC, FPGA, Controlador, SoC
	+ Limitações:
		+ Transistors no longer getting much better because of the slowing of Moore’s Law and the end of Dinnard scaling,
		+ the unchanging power budgets for microprocessors,
		+ the replacement of the single power-hungry processor with several energyefficient processors, and
		+ the limits to multiprocessing to achieve Amdahl’s Law
	+ Mudanças:
		+ Adoção de cores de função específica
	+ Termos:
		+ Yield - quantidade de processadores que não apresentam defeitos no processo de fabricação
	+ Benchmarks

### Dia 2

+ Módulo 5: Placa Mãe (MOBO)
	+ Partes da Placa Mãe (o que é responsável pelo que)
		+ [Techcore](https://www.techchore.com/parts-motherboard-functions/)
		+ [Computer Hope](https://www.computerhope.com/jargon/m/mothboar.htm)
		+ [TechGujarati](https://techgujarati.com/en/computers-en/motherboard-the-most-important-part-of-pc/)
		+ Componentes/Informações:
			+ Modelo
				+ Informações que se obtem a partir dele são muito importantes (versão, arquitetura, família)
			+ Socket da CPU 
			+ Slots de Memória
			+ Sata e NVME
			+ Conectores PCI e PCI Express
			+ Conectores de Fans
			+ Conector de Energia ATX (24 Pinos)
			+ CMOS
			+ I/O
			+ North Bridge
			+ South Bridge
			+ Chipset
			+ Outras portas (ATA, USB, etc)
		+ Overclocking (VRMs)
		+ PCI e Barramento
			+ Velocidade do barramento (GT/s)
+ Módulo 6: Processador (CPU) 
	+ Como os chips estão organizados dentro do computador
	+ Packaging
		+ [PcMAG](https://www.pcmag.com/encyclopedia/term/chip-package)
		+ [Packaging e Tipos de Chips](https://faculty.eng.ufl.edu/navid-asadi/wp-content/uploads/sites/84/2021/09/Lecture-9-Packaging-1-3.pdf) 
		+ [Milennium Circuits Limited](https://www.mclpcb.com/blog/ic-packaging-information/)
		+ [SemiEngineering](https://semiengineering.com/knowledge_centers/packaging/)
		+ [McKinsey](https://www.mckinsey.com/industries/semiconductors/our-insights/advanced-chip-packaging-how-manufacturers-can-play-to-win)       
	+ Cache
		+ Hierarquia de Caches
		+ Disposição das Caches no processador
	+ ALU
		+ 
	+ Núcleo VS Thread
	+ Manufacturers
		+ AMD, Intel, Apple, Arm, HiSilicon, Hitachi, MediaTek, Nvidia, Zhaxin, Loongson, Texas Instruments, SiFive, Samsung, Qualcomm, Fujitsu, Broadcom, Baikal
	+ Desafios atuais de hardware (30 min)
		+ Fim da Lei de Moore
		+ HDs não crescem em capacidade
		+ Temperatura de componentes e consumo de energia
	+ TDP (Thermal Design Power)

### Dia 3

+ Módulo 7: Placa de Vídeo (GPU)
    + Lógica:
		+ Unidades de processamento com propósito especifico
		+ GPU integrada ou dedicada
	+ Estrutura:
		+ [AskThatBlog](https://www.akshatblog.com/graphics-card-components-explained-in-detail/)
		+ [PaperSpace](https://blog.paperspace.com/a-complete-anatomy-of-a-graphics-card-case-study-of-the-nvidia-a100/)
		+ [TechSpot](https://www.techspot.com/article/1988-anatomy-graphics-card/)
		+ [Utmel](https://www.utmel.com/blog/categories/integrated%20circuit/graphics-card-explained-classification-working-and-structure)
		+ [FreeContent](https://freecontent.manning.com/getting-to-know-gpus/)
		+ Processadores de GPU 
		+ VRAM (GDDR)
		+ VRM
		+ Interconnect
		+ I/O
		+ Pino de Alimentação
			+ Meltdown (12VHPWR)
			+ [Electronics](https://electronics.stackexchange.com/questions/182841/why-do-graphics-card-power-cables-pcie-etc-use-more-than-two-wires)
			+ [gpumag](https://www.gpumag.com/gpu-power-connectors-explained/)
			+ [pactech](https://pactech-inc.com/difference-between-6-pin-8-pin-12-pin-gpu-cable/)
			+ [sense pin](https://electronics.stackexchange.com/questions/339033/what-is-the-use-of-sense-and-in-a-psu)
	+ Componentes de baixo nível
		+ FP32 units
		+ FP64 and/or SPU (Specialized Procesing Unit)
		+ INT32 units
		+ Registers
		+ on-chip memory: 
			+ L0$ (rarely in consumer class hardware),
			+ L1$ used with Shared Memory per compute unit
			+ L2$ per GPU
		+ off-chip memory (device memory)
		+ instruction scheduler
		+ instruction dispatcher
		+ TMUs, ROPs - fixed pipeline units
		+ [vksegfault](https://vksegfault.github.io//posts/gentle-intro-gpu-inner-workings/)
	+ Desafios
		+ Baixa taxa de transferência entre a CPU e a GPU (low bus bandwidth)
		+ Nomenclaturas (cada empresa usa as suas)
			+ Compute Units (CU/AMD e Intel) ou Streaming Multiprocessors (SMs/Nvidia)
    + Fabricantes:
		+ Amd, Nvidia, Intel, Moore Threads, Qualcomm
	+ Tendências:
		+ Aumento na demanda de Energia
+ Módulo 8: Memória (RAM) 
	+ RAM = "Random Access Memory"
    + Controladora
    + Chips e sua estrutura interna (CAS, RAS)
	+ In-Memory Computing
	+ Memória ECC (Error Correcting Code)
	+ Parâmetros de performance
		+ CAS
		+ RAS
		+ Largura de Banda
	+ JEDEC
	+ XMP (Overclocking predefinido da Intel)   
		+ [PcGamer](https://www.pcgamer.com/what-are-xmp-profiles-and-how-do-i-use-them/)
	+ Técnicas para melhoria da performance
		+ Out of order execution
		+ Cache
		+ Prefetching
			+ Faz predição à partir de padrões de requisições
			+ Também é possível fazer prefetching por software, mas somente em alguns casos
+ Módulo 9: Discos Rídigos e Sólidos (HDDs e SSDs)
    + Controladora de disco
    + Estrutura de Leitura
    + Os discos em Si
	+ Baixos ganhos de performance
		+ HAMR
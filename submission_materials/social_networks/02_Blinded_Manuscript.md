**The Modern Telephone: Information Mutation in Machine-to-Machine Communication Networks**

**Abstract**

Social network diffusion models typically treat nodes as perfect relays. We test this assumption in machine-to-machine (M2M) networks by simulating information transmission through six topologies of large language model agents (5,880 transmissions across 420 chains). Network topology is the primary determinant of semantic mutation, shaping not only its magnitude but its type: linear chains generate drift; synthesis structures maximize cross-lineage divergence; hierarchies minimize fabrication. Capability placement at structurally consequential nodes reduces fabrication, but explicit capability labels do not improve synthesis. M2M networks are therefore not neutral conduits but topology-specific processors of meaning, with implications for AI-mediated organizational communication.

**Keywords:** machine-to-machine communication; social networks; information diffusion; network topology; semantic fidelity; fabrication

**Introduction**

In 1972, a child at one end of a schoolyard whispers a sentence to the
child beside her. By the time the sentence reaches the far end, it has
been transformed beyond recognition. The children\'s game of telephone
has served as an organizing metaphor for research on information
diffusion across social networks. This is not because adults play it
knowingly, but because the same basic process operates whenever
information passes from person to person through a chain of imperfect
human relays. Each transmission introduces the possibility of error,
each error compounds the last, and the message that arrives at the
network\'s periphery may share little meaning with the one that departed
from its center. This is not a trivial finding. It has implications for
how we understand the spread of beliefs and behaviors, the maintenance
of cultural diversity, the limits of organizational control over
information, and the practical reachability of networks that are
otherwise well-connected.

Brashears and Gladstone (2016) formalized this intuition. In a series of
laboratory and crowdsourced experiments using human subjects, they
demonstrated that semantic errors accumulate rapidly as messages
traverse social networks, that efforts to correct these errors
paradoxically produce more mutant forms of the original contagion
than uncorrected transmission, and that the format of a message shapes
its robustness against error. Human cognitive limits were the engine of
these effects: the working memory constraints, attentional limits, and
meaning-seeking tendencies of human nodes produced systematic and
theoretically predictable patterns of information mutation. The network,
in Podolny\'s (2001) terms, was not merely a pipe through which
information flowed unchanged. It was a processor, transforming what
passed through it.

That work was conducted at a moment when networks were still
predominantly composed of human nodes. In the intervening decade, a
growing class of organizational workflows has come to route information
through sequences of LLM-mediated transformations before human review.
Machine-to-machine communication, in which large language model (LLM)
agents receive, process, and relay information with minimal or no human
involvement at intermediate stages, is now a common pathway through
which consequential organizational information flows. A contract may
pass through AI translation, AI summarization, AI compliance checking,
and AI formatting before a lawyer reads it. A customer inquiry may pass
through intent classification, knowledge retrieval, response generation,
and tone adjustment before reaching the customer. An analyst may
receive a briefing synthesized by a central AI from the outputs of
several specialized data agents. A manager may act on a report whose
underlying data traversed multiple AI processing stages before producing
the narrative she reads. In each of these cases, information has passed
through a network of artificial nodes whose properties differ
fundamentally from human ones: they do not forget, do not misread, do
not tire. But they do transform, and they transform in systematic and
consequential ways.

The proliferation of M2M communication raises questions that existing
network diffusion research is not equipped to answer. How does
information mutate as it traverses chains of LLM agents? Does the
structure of the network, the topology through which information
flows, shape the character and magnitude of that mutation? When
multiple AI agents process the same information and their outputs must
be reconciled, whose version prevails, and on what basis? Do networks
that include humans at specific structural positions behave differently
from fully automated ones, and does the position of the human in the
network matter? These are not merely academic questions. The
organizations that route critical decisions through AI pipelines, the
platforms that deliver AI-processed information to millions of users,
the clinical systems that synthesize patient data through multiple AI
layers before a physician reviews it. All have a stake in
understanding whether, how, and in what direction information mutates as
it traverses these structures.

The emerging literature on LLM-based information processing has begun to
touch these questions from adjacent directions. Work on the LLM
telephone game (Mohamed et al., 2025; Perez et al., 2024; Yax et al., 2025) has established
that iterative LLM generation distorts information, and that different
model architectures produce different attractor states, stable mutant
forms toward which iterative chains converge. Research on AI-mediated
communication (Hancock, Naaman, & Levy, 2020; Sundar, 2020) has examined
how AI tools that modify or generate human messages affect interpersonal
dynamics and trust. Work on emergent social conventions in LLM
populations (Ashery et al., 2025) has shown that groups of AI agents can
develop norms, generate bias, and exhibit critical mass dynamics. The
multi-agent systems literature has documented how error propagates
through chains of LLM agents and how network structure affects
collaborative task performance (Tran et al., 2025). A growing body of
survey work has catalogued hallucination in LLM-based agents, specifically the
generation of confident, fluent content that is factually unsupported or
untraceable to inputs, identifying it as a pervasive feature of
agentic systems that intensifies under multi-step reasoning and
multi-agent coordination (Lin et al., 2025; Alansari & Luqman, 2025). Most
directly adjacent to the present work, recent mathematical modeling has
established that network topology produces systematic signatures in how
local transmission errors accumulate across canonical graph structures,
with hub-mediated integration suppressing distortion in scale-free
networks and balanced clustering reducing it in small-world structures
(Sur et al., 2025). This mathematical work establishes topology as a
consequential determinant of information distortion; our contribution is
to move from formal models of generic nodes to empirical simulation of
LLM agents, distinguishing three qualitatively distinct mutation types (drift, divergence, and fabrication) that formal distortion models do
not capture and that carry different practical implications for
organizational AI design. What is missing from all prior work is
precisely what the social network diffusion literature provides: a
theoretically grounded, empirically systematic account of how network
topology shapes information mutation in networks of LLM agents, measured
at the level of semantic meaning, across a range of structures that
reflects the real diversity of M2M communication systems.

We provide that account here. Drawing on the original Brashears and
Gladstone (2016) framework as both theoretical foundation and human
baseline, we examine information diffusion across six representative
fully automated M2M network topologies. We introduce *machine
authority* as an umbrella term for authority-like weighting of machine
outputs, and we decompose it analytically into four constructs that
need to be kept separate—*capability placement* (assigning a
higher-capability model to a single structurally consequential node,
such as a hub or hierarchy apex), *capability asymmetry* (assigning a
higher-capability model to one of multiple parallel inputs converging
at a synthesis node, as in lattice and bidirectional lattice
configurations), *capability disclosure* (explicitly indicating to a
downstream node that an input came from a higher-capability model), and
*authority-like adoption* (preferential incorporation of the
higher-capability source\'s content into downstream outputs). Only the
last is directly analogous to deference in human status systems; the
first two are processing-capability effects and the third is a
source-labeling manipulation. We employ a fully synthetic experimental
pipeline in which LLM agents serve as both network nodes and semantic
coders, and we measure information mutation along multiple dimensions,
including semantic fidelity, factual retention, informational
completeness, diversification trajectory, and content-incorporation
patterns at synthesis nodes, that collectively characterize how
information is transformed as it flows through networks of artificial
nodes.

The contribution is threefold. Theoretically, we extend information
diffusion research to M2M networks and distinguish topology-induced
mutation types from capability-configuration effects. Methodologically, we
show how synthetic LLM pipelines can be used to compare diffusion
architectures while separating capability placement from capability
disclosure. Empirically, we show that topology is the primary
determinant of drift, divergence, and fabrication, while capability
placement reduces fabrication only in structurally amplified positions
and explicit capability disclosure has little effect on synthesis
outcomes under the tested conditions. To our knowledge, this is the
first topology-comparative account of semantic fidelity and
diversification across this range of M2M architectures, though we
recognize the field is moving quickly enough that any firstness claim
should be read narrowly.

**Background**

Research on the diffusion of information, beliefs, and behaviors through
social networks has a long and productive history. From the early
studies of hybrid corn adoption (Ryan & Gross, 1943) and antibiotic
diffusion among physicians (Coleman, Katz, & Menzel, 1966) to
contemporary work on health behaviors (Centola, 2010, 2011),
organizational practices (Wang & Soule, 2012), and political
mobilization (Bond et al., 2012), diffusion research has consistently
found that social networks are consequential conduits for the spread of
social contagions, entities that are both transferable and
duplicable, meaning they can be passed from person to person without the
giver losing possession (Schaefer, 2007). The structure of the network
shapes the speed, reach, and character of diffusion. The pattern of ties, the positions of nodes, the presence or absence
of weak ties and structural holes all play a role (Borgatti & Foster, 2003; Granovetter, 1973; Burt, 1992; Centola & Macy,
2007).

What this literature has consistently treated as a background assumption
is the fidelity of transmission. Nodes in social network models receive
a contagion and pass it on unchanged, or they do not pass it on at all.
The possibility that the contagion is transformed in transit, that
the message arriving at one side of the network differs semantically
from the message that departed from the other, has been largely
excluded from formal models (Carley, 1991; Centola & Macy, 2007;
Rodriguez et al., 2014). As Brashears and Gladstone (2016) noted, this
exclusion is not theoretically motivated: it is a convenience that
simplifies modeling at the cost of ecological validity.

The empirical record suggests the exclusion is costly. Brashears and
Gladstone (2016) demonstrated in a controlled experiment that semantic
errors accumulate rapidly as messages pass through chains of human
subjects. Three findings from that work are directly relevant here.
First, the format of a message shapes its error robustness:
lower-entropy messages (standard English, approximately 75% redundant by
Shannon\'s (1950) estimate) preserve semantic content more effectively
than higher-entropy formats (text messaging pidgin) despite the greater
surface area for error in the former. The redundancy of natural language
provides a basis for reconstruction that compressed formats deny.
Second, human efforts to correct perceived errors in received
messages, a natural and ubiquitous behavior, paradoxically produce greater
semantic diversification than uncorrected transmission. Error correction
preserves the grammatical and syntactic integrity of messages, producing
valid mutant forms that downstream recipients cannot identify as
mutations and thus transmit as though original. Third, and most
consequentially for the current work, these effects are not merely
local: they compound across transmission chains, such that the effective
semantic reachability of social networks, meaning how much of the original
meaning survives to distant nodes, is substantially lower than
structural analyses of those networks would suggest.

The Brashears and Gladstone (2016) framework distinguished two distinct
failure modes of information transmission. Corruption occurs when errors
accumulate without correction, producing messages that are recognizably
degraded. These messages are grammatically and syntactically irregular, obviously
different from any coherent original. Diversification occurs when error
correction is operative, producing messages that are grammatically and
syntactically valid but semantically distinct from the original.
These mutant forms propagate silently because their deviations are
invisible to downstream recipients. These are not merely different
degrees of the same phenomenon: they have different structural
signatures (corruption produces high consecutive fidelity in later chain
positions as a stable corrupt form locks in; diversification produces
high cross-lineage variance as different correction attempts produce
different valid alternatives), different implications for network
dynamics (corruption limits reach; diversification multiplies competing
versions), and different practical consequences (corrupt messages are
recognizably wrong; diversified messages are convincingly
authoritative).

This framework was developed for human networks. The question motivating
the present work is whether, and how, it extends to machine networks,
and whether the extension reveals new phenomena that the human case
obscures.

**M2M Communication**

The term machine-to-machine communication, as used in this paper, refers
to the processing and relay of information by artificial agents,
specifically large language model (LLM) agents, with minimal or no
human involvement at intermediate stages. This is distinct from the
engineering literature\'s use of the term to describe device-to-device
data transmission in IoT and telecommunications contexts (e.g., 3GPP
standards for M2M protocols). We are concerned with semantic M2M
communication: the transformation of meaningful content as it passes
through networks of LLM agents that read, interpret, and regenerate
text. The defining feature of this communication mode is that AI agents
do not merely relay information. They transform it, and that
transformation is governed by the agent\'s training, architecture, and
prompt context rather than human cognitive processes.

Hancock, Naaman, and Levy (2020) defined AI-mediated communication
(AI-MC) as interpersonal communication in which a computational agent
modifies, augments, or generates messages to accomplish communication
goals. Their framework situated AI as a mediator of human-to-human
communication, a tool through which humans communicate with each
other, with AI transforming the message in transit. This captures an
important and growing phenomenon: autocomplete, smart reply, AI drafting
assistants, grammar correction, and summarization tools all constitute
AI-mediated human communication. But the concept of AI-MC as Hancock and
colleagues defined it preserves the human as the communicative agent,
with AI in a supporting role.

The configuration we examine is both broader and, in important respects,
more fundamental. In the M2M networks we study, AI agents are themselves
the communicative agents for substantial portions of the information
processing chain. Humans may initiate the chain (by providing a seed
document or query), and they may receive its output (by reading a
summary or acting on a recommendation), but the intermediate processing
(which may involve many transformations across many nodes) is
conducted entirely by artificial agents. The human is the source and the
sink; the network is artificial. This is not a futuristic scenario: it
describes the current operation of enterprise AI pipelines, multi-agent
coding assistants, automated research synthesis tools, clinical decision
support systems, and a growing range of organizational knowledge
management applications.

The significance of this configuration for information diffusion theory
is straightforward: if information is systematically transformed as it
passes through AI nodes, and if that transformation is shaped by network
structure, then organizations and systems that route consequential
information through AI pipelines face the same fundamental problem that
Brashears and Gladstone (2016) identified for human networks. The
effective semantic reachability of their networks may be substantially
lower than they believe. A clinical AI system that routes patient
information through three processing stages before a physician reviews
it may deliver semantically degraded summaries. An enterprise knowledge
management system that synthesizes departmental outputs through a
central AI hub may deliver homogenized or biased versions of the
original documents. A multi-agent research synthesis pipeline may
deliver conclusions that differ from those in the underlying literature.
Understanding the topology-dependence of these effects is a practical
imperative as well as a theoretical one.

**Network Topologies**

M2M communication systems exhibit diverse network topologies, each with
distinct structural properties that, we argue, produce distinct patterns
of information mutation. We organize the topology space along several
theoretical dimensions: transmission path length (the number of AI
processing steps a message traverses), input multiplicity (whether nodes
receive single or multiple inputs requiring synthesis), centralization
(whether processing is concentrated at privileged nodes), and
directionality (whether information flows unidirectionally or with
iterative feedback). A further dimension—human placement—shapes hybrid
human-machine networks; we discuss it briefly below for completeness,
although the present study restricts its empirical scope to fully
automated structures and is not designed to estimate human-placement
effects.

We describe below the taxonomy of topologically relevant M2M structures,
organized by structural class. This taxonomy serves as the theoretical
basis for our network selection in subsequent sections.

***Sequential Structures***

The *linear chain* is the simplest and most ubiquitous M2M structure.
Each node receives a single input, processes it, and passes the output
to the next node. Path length scales with chain length; input
multiplicity is uniformly one; no synthesis decisions occur. In
practice, linear chains describe the majority of enterprise document
workflows: a contract passes through AI translation, AI summarization,
AI compliance review, and AI formatting before a human reads it. Medical
record processing follows the same logic, as do software development
pipelines (code passing through AI static analysis, documentation
generation, and security scanning), customer service escalation chains,
and academic manuscript processing workflows. The linear chain is the
M2M analog of the human telephone game and provides the baseline against
which other topologies are measured.

The *ring* extends the linear chain into a closed loop, introducing
cyclicality. Nodes are connected in a circle; information can traverse
multiple paths to reach any given node. Ring structures model federated
AI learning networks, where models at different organizational nodes
each process local data and share updates around the ring without
central coordination. Distributed AI moderation networks, where content
assessment passes from one moderation agent to the next around a ring,
also exhibit this structure. The ring\'s theoretical significance is
that messages can arrive at a node having traveled different numbers of
hops from the same origin, potentially in different mutated forms,
creating conditions for local reconciliation of divergent versions.

The *ring with shortcuts*, equivalent to the small-world network
structure of Watts and Strogatz (1998), adds direct connections
between non-adjacent nodes to a ring backbone. Most real distributed AI
systems evolve toward this structure as high-frequency communication
patterns produce persistent connections that bypass the ring. Enterprise
knowledge graphs with cross-departmental links, social media
recommendation networks with long-range algorithmic connections, and
multi-datacenter AI deployments with high-bandwidth regional shortcuts
all exhibit small-world topology. The structural significance of
shortcuts is that they reduce mean path length substantially while
preserving local clustering, meaning that some messages traverse short
paths while others traverse long ones, producing bimodal
distributions of fidelity at terminal nodes.

***Centralized Structures***

The *hub-and-spoke* structure places a single high-capacity node at the
center, with all information routing through it before reaching
peripheral nodes. Hub-and-spoke is the dominant organizational AI
deployment model: a powerful central model (typically a frontier-class
LLM such as GPT-4 or Claude Opus) receives all inputs, processes them,
and distributes outputs to peripheral specialized models or human-facing
interfaces. Enterprise AI assistant deployments, organizational
knowledge management systems where a central AI synthesizes all
departmental outputs, intelligence analysis fusion centers, and supply
chain management platforms with a central decisioning AI all exhibit
hub-and-spoke topology. The hub\'s processing is consequential for every
message in the network. Its model identity, capability, and biases
are structurally amplified. The hub is therefore a paradigm site for
capability placement, one of the capability-configuration constructs we
develop below.

The *directed hierarchy* extends hub-and-spoke into a multi-tiered
structure in which information flows strictly downward from upper to
lower tiers. Each tier receives processed outputs from the tier above,
transforms them, and passes them to the tier below. Directed
hierarchies model organizational AI systems that mirror human
organizational charts: a strategic-planning AI at the apex processes
high-level inputs and produces directives, departmental AI models
operationalize those directives into plans, team-level AI tools
decompose plans into tasks, and execution-level AI agents act.
Military command-and-control AI systems, large-scale content production
pipelines (strategy AI → creative AI → production AI → distribution AI),
regulatory compliance processing systems, and healthcare protocol
systems (clinical guideline AI → specialist AI → point-of-care AI) all
exhibit directed hierarchical topology. Hierarchies are *structurally*
tiered by design: upper-tier outputs constrain lower-tier processing,
creating a top-down cascade. Whether the hierarchy is also
*capability-ordered* (i.e., whether higher tiers run higher-capability
models) is a separate question and a manipulation in this study. The
combination of structural tiering and capability ordering is the
condition under which we expect the strongest amplification of
upper-tier text properties through the cascade.

***Redundant and Synthesis Structures***

The *lattice* or parallel crossing network, as studied by Gladstone
(2016) in the human network context, consists of two or more parallel
linear chains whose outputs periodically merge at synthesis nodes. Each
synthesis node receives multiple inputs from parallel chains and must
produce a single output, creating an explicit reconciliation decision.
Lattice structures model dual-vendor AI pipelines (organizations routing
the same document through competing AI vendors simultaneously and
reconciling outputs before acting), parallel translation and
back-translation quality control workflows, redundant risk assessment
systems in regulated industries (two independent AI risk models
processing the same data with human-mandated reconciliation), A/B
content generation pipelines, and collaborative AI coding systems where
multiple agents independently attempt the same task and a synthesis
agent reconciles their solutions. The lattice is theoretically important
because the synthesis decision (which version to adopt, and how to
combine them) is the structural location at which capability disclosure
can be tested independently of capability placement, and at which
authority-like adoption can be observed.

The *bidirectional lattice* extends the lattice by allowing
back-communication: nodes can query predecessors, request clarification,
and revise based on feedback. This is the structure of multi-agent
debate systems, where AI agents argue, critique, and revise through
multiple rounds before converging on an output. AutoGen, CrewAI, and
similar multi-agent frameworks implement this structure by default.
Legal document drafting systems that employ AI advocates and AI critics
in iterative dialogue, AI red team/blue team security assessment
workflows, and collaborative AI diagnostic systems where agents argue
for competing clinical assessments and converge through debate all
exhibit bidirectional lattice topology. The bidirectional structure
theoretically reduces corruption (back-communication allows error
detection and correction) while potentially increasing diversification
(iterative debate can amplify initial differences before converging).

***Hybrid Human-Machine Structures (Boundary Conditions)***

Two hybrid configurations modify the fully automated cases by inserting
human nodes at specific structural positions. In *human-terminal*
networks, AI nodes compose the entire intermediate processing chain and
a human agent is the terminal receiver, acting on whatever the chain
produced (e.g., the email thread summarized by an AI assistant before
the recipient reads it, the analytics report generated by a pipeline of
AI processing steps and presented to a manager as the basis for
decision-making). In *human-checkpoint* networks, a human agent appears
at an intermediate position as an approval gate that determines what
propagates downstream (e.g., legal document review, content moderation
with human review of borderline cases, physician approval of
AI-generated medication orders). The theoretical significance of these
configurations lies in *where* human judgment enters: terminal placement
exposes the human to whatever has accumulated through the chain, while
intermediate placement creates an asymmetry in which upstream mutations
are exposed to potential human correction but downstream mutations are
not. We treat hybrid configurations as boundary conditions for the
present study; they warrant systematic investigation but lie outside the
empirical scope of this paper, which restricts itself to fully automated
structures so that AI network effects can be estimated without confounds
from human-AI interaction.

**Machine Authority**

Status Characteristics Theory (Berger, Cohen, & Zelditch, 1972; Berger,
Fisek, Norman, & Zelditch, 1977) argues that diffuse and specific status
characteristics shape performance expectations in task groups, which in
turn affect influence, evaluation, and the adoption of contributions.
The analogy to M2M networks is limited but analytically useful. LLM
agents do not possess human status characteristics, nor do they
participate in the interactional processes through which status beliefs
are reproduced. They do, however, differ in capability, specialization,
provenance, and reliability histories. We therefore treat *machine
authority* not as machine status in the full SCT sense, but as a
restricted mechanism: differential weighting of machine outputs based on
capability-linked properties of the generated text or on explicit
capability cues attached to that text. We use the term only as an
umbrella; where the manuscript discusses a specific mechanism we use
the narrower term that matches it.

Within this restricted framing, we distinguish four constructs that
need to be kept separate. Two of them (placement and asymmetry) are
configurations of capability differences in the network; one
(disclosure) is a labeling manipulation; and one (authority-like
adoption) is the empirical outcome variable on which the SCT analogy
ultimately stands or falls.

*Capability placement* refers to assigning a higher-capability model to
a single structurally consequential node, such as the hub in a
hub-and-spoke network or the upper tier of a directed hierarchy.
Capability placement is positional: the upgraded node\'s outputs
propagate to many downstream positions because of its structural
location. The mechanism does not require any source labeling and does
not require deference; it requires only that the better model produces
better text, which then constrains downstream processing across the
network.

*Capability asymmetry* refers to assigning a higher-capability model to
one of two or more parallel inputs that converge at a downstream
synthesis node, such as Chain A versus Chain B in a lattice or
bidirectional lattice. Capability asymmetry differs from capability
placement in that the upgraded model is not at a single structurally
amplified position but on one of several parallel paths whose outputs
the synthesis node must reconcile. Like placement, asymmetry can produce
downstream effects through input quality alone, without any disclosure
or deference; unlike placement, its downstream reach is bounded by the
synthesis decision rather than by network-wide propagation.

*Capability disclosure* refers to explicit metadata or system-prompt
notation indicating to a downstream node that an input originated from a
higher-capability system. Capability disclosure is a source-labeling
manipulation. Of the mechanisms, it is the closest parallel to SCT, in
that an explicit cue is present and can in principle influence adoption
independent of output quality. Real M2M systems that implement
model-routing metadata, confidence scores, or source attribution
accomplish this: the downstream node is, in effect, told whose input
should be weighted more heavily.

*Authority-like adoption* refers to the actual, observable preferential
incorporation of a higher-capability source\'s content into a downstream
node\'s output, especially when content quality or substance is held
constant. This is the only one of the mechanisms that is directly
analogous to deference in human status systems: it asks whether a
synthesis node weights an input more heavily because it came from a
higher-capability source, holding text properties as fixed as the design
permits.

These mechanisms are not synonymous. Capability placement, capability
asymmetry, and capability disclosure are design choices about how the
network is configured; authority-like adoption is an empirical pattern
that may or may not result. Capability placement and capability
asymmetry can both produce downstream quality improvements without any
deference whatsoever, simply by improving the text that downstream
nodes receive. Capability disclosure tests whether a label, beyond text
properties, additionally moves adoption. Authority-like adoption is the
outcome variable on which the SCT analogy ultimately stands or falls.

The bases on which capability-linked differential weighting could
operate are multiple and theoretically distinguishable, although the
present study tests only model capability tier. Model capability tier is
the most direct analog to task-specific status in SCT: frontier-class
models (GPT-4, Claude Opus, Gemini Ultra) are widely understood, within
the organizations and systems that deploy them, to have higher general
information processing capacity than smaller, cheaper, or more
specialized models. Institutional affiliation refers to the
organizational or commercial imprimatur attached to a model, whether it
was developed by a major research laboratory, deployed through an
enterprise contract, or is an open-source alternative. Domain
specialization refers to the degree to which a model is designed for or
fine-tuned on a specific task domain. Perceived accuracy refers to the
track record of a model\'s outputs as experienced by human overseers or
measured by automated evaluation systems. The present study
operationalizes capability tier directly; the other bases lie outside
its empirical scope and are addressed in the limitations section as
future-work directions.

In any given M2M network, different nodes may have different
capability-linked profiles. A hub in a hub-and-spoke system may be a
frontier-class general-purpose model while spokes are smaller
task-specific models; the hub\'s structural position then amplifies
whatever capability advantage that model has. In a *capability-ordered*
directed hierarchy—the manipulated condition tested here—capability
descends with position by design, generating a downward gradient;
hierarchies are not inherently capability-ordered, and the standard
condition holds capability uniform across tiers. In a lattice with
parallel chains of different model types, synthesis nodes face decisions
about which chain\'s output to adopt or how to weight them—the
structural location at which capability disclosure could in principle
exert effects beyond capability asymmetry alone.

**Structural Conditions**

The three mechanisms operate under different structural conditions.
*Capability placement* operates wherever a higher-capability model
occupies a structurally consequential node. Its effects propagate
through the quality of the text the upgraded node generates and forwards
to downstream positions, regardless of whether downstream nodes face
multi-input decisions. Hub-and-spoke and directed hierarchy
configurations make capability placement structurally amplified: a
single upgraded node\'s output reaches many downstream nodes through the
network\'s routing geometry.

*Capability disclosure* and *authority-like adoption*, by contrast,
require a structural condition that capability placement does not: a
node that receives multiple inputs and must produce a single output, so
that there is something to weight or to defer to. This is the
*synthesis node*. In linear chains and rings, every node is a
single-input relay; there is nothing to defer to and nothing for a
disclosure label to operate on. Synthesis nodes appear in lattice and
bidirectional lattice structures (where parallel chains converge),
in hub-and-spoke structures (where the hub integrates many spokes), and
in human-checkpoint structures (which lie outside the present empirical
scope).

The implicit/declared distinction we use in the empirical design maps
directly onto this analytic decomposition. In hub-and-spoke and directed
hierarchy structures, the manipulation is positional and operates as
*capability placement*: a single higher-capability model occupies the
hub or upper tier and there is no competing input at which a label
would be operative. In lattice and bidirectional lattice structures,
where parallel chains of potentially different quality converge at a
synthesis node, the manipulation operates as *capability asymmetry*,
and capability disclosure becomes empirically separable from asymmetry
itself. We therefore implement two conditions in those topologies: an
*implicit* condition (capability asymmetry between chains, no
disclosure to the synthesis node) and a *declared* condition (the same
asymmetry plus an explicit capability label to the synthesis node). The
implicit-versus-standard contrast isolates capability asymmetry; the
declared-versus-implicit contrast isolates capability disclosure on top
of asymmetry; and the resulting incorporation pattern at the synthesis
node is the test of authority-like adoption.

This structural decomposition generates two distinct empirical
predictions. First, capability-placement effects (hub, hierarchy) and
capability-asymmetry effects (lattice, bilattice) on information
mutation should be observable in any topology where the upgraded
node\'s outputs reach a structurally consequential downstream position,
with effect sizes scaling with the structural amplification of that
position—largest where placement reaches many downstream nodes, smaller
where asymmetry feeds into a single synthesis node. Second, capability
disclosure should produce additional movement beyond asymmetry only if
synthesis nodes respond to the label beyond the text properties of
their inputs—an empirical question rather than a foregone conclusion. If frontier-class
models have distinctive stylistic or semantic biases, toward formality,
specificity, or particular topical framings, as the model culture
literature suggests (Brinkmann et al., 2023), then networks that route
synthesis decisions through high-capability nodes should additionally
produce systematic drift in those directions across the network,
regardless of whether the disclosure label is present.

**Joint Effects**

The joint effects of network topology and capability-linked
configurations on information mutation are not simply additive. The
topology determines where capability placement can be structurally
amplified and where capability disclosure has a synthesis node to
operate on; the configuration determines what happens at those
structural locations. A hub-and-spoke network with a higher-capability
hub produces different mutation dynamics than one with a
standard-capability hub, not merely in the magnitude but in the
direction of mutation: the hub\'s semantic preferences propagate outward
to all downstream nodes, homogenizing the network toward its attractor.
A directed hierarchy with higher-capability nodes at upper tiers
produces downward cascades in which upper-tier text properties are
amplified as they propagate through successive processing stages. A
lattice with capability asymmetry between parallel chains produces
synthesis decisions that may systematically favor one chain\'s outputs,
selectively incorporating the mutations it has accumulated while
discarding those of the other.

These joint effects have practical implications that extend beyond
information fidelity per se. Organizations that deploy hub-and-spoke AI
architectures with a single higher-capability central model are not
merely routing information efficiently; they are structurally amplifying
that model\'s semantic tendencies throughout the organization\'s
information environment. Directed hierarchies with capability-ordered
tiers create cascade effects where text properties introduced at upper
tiers cannot be readily corrected at lower tiers, which process
constrained by upper-tier outputs. Lattice networks with
capability-asymmetric parallel chains may perform better on average
fidelity (the higher-capability chain\'s outputs are more likely to be
incorporated) while producing systematic rather than random mutation
(errors track the characteristics of the higher-capability model).
Understanding these joint effects requires studying topology and
capability configuration together, not separately.

**Network Selection**

The taxonomy of M2M network structures described above encompasses a
large and theoretically relevant design space. No single study can
investigate all of it. We select six topologies that collectively
provide coverage of the two theoretical dimensions most consequential
for information mutation, transmission path structure and input
multiplicity, while representing the empirically most prevalent fully
automated M2M structures in contemporary organizational and social life.
The six selected topologies are organized into three structural classes
of two topologies each. Within each class, one structural dimension is
held constant while a theoretically relevant property is varied,
allowing clean within-class comparisons. Across classes, the dimension
of primary variation differs, allowing the joint effects of multiple
structural properties to be assessed.

We restrict the present study to fully automated M2M networks,
structures composed entirely of AI nodes, with no human agents at
intermediate positions. This restriction is deliberate and theoretically
motivated. The present study\'s central claim concerns how AI network
structure per se shapes information mutation. Introducing human agents
at specific structural positions would confound this question with
questions about human-AI interaction that, while important, are
theoretically distinct and best addressed as a subsequent study. The
fully automated restriction also ensures that the synthetic pipeline
methodology is internally consistent: we study AI networks using AI
agents, with no requirement to simulate or recruit human participants.

**Sequential Structures**

The first class comprises the linear chain and the hub-and-spoke
network. Both structures route information through single-input nodes
with no synthesis decisions. Each node receives one input, processes
it, and passes to the next. Both are fully automated. They differ on
centralization: in the linear chain, information flows through a uniform
sequence of nodes with no privileged position; in hub-and-spoke, all
information routes through a single central node before reaching
peripheral nodes, making the hub\'s processing consequential for every
message in the network.

The linear chain is selected as the foundational baseline, providing the
M2M analog to the human linear network studied by Brashears and
Gladstone (2016). It is among the most prevalent single M2M structures
in current organizational deployment and provides the comparison point
against which other topologies are assessed. The hub-and-spoke is
selected because it describes a dominant enterprise AI deployment
architecture (a central model receiving inputs, processing them, and
distributing to peripheral specialized agents or human-facing
interfaces) and provides the primary test of centralization effects on
information mutation. Capability placement is manipulated in the
hub-and-spoke condition by varying the capability tier of the hub model,
testing whether positional placement at the structurally amplified
central node shapes both the direction and character of mutation across
the network.

**Synthesis Structures**

The second class comprises the lattice and the bidirectional lattice.
Both structures create synthesis nodes where multiple inputs must be
reconciled into a single output. This is the defining structural feature that
distinguishes synthesis structures from sequential ones. They differ on
iterativity: the unidirectional lattice routes information in a single
forward pass, with synthesis nodes receiving inputs from parallel chains
and producing outputs that flow downstream; the bidirectional lattice
allows back-communication, with agents able to revise based on feedback
from neighbors across multiple rounds before the output is finalized.

The lattice is selected for theoretical continuity with the dissertation
work of Gladstone (2016), which studied a human lattice network and found
elevated error accumulation relative to the linear baseline, and because
it represents the dual-vendor AI pipeline, redundant processing, and
parallel synthesis configurations increasingly common in regulated
industries. The bidirectional lattice is selected because it represents
the multi-agent debate and collaborative AI structures that have
proliferated with the adoption of frameworks such as AutoGen and CrewAI
(structures in which iterative back-communication is the default), and
because its iterative synthesis dynamic generates competing predictions
relative to the unidirectional case. Within both lattice conditions, the
capability configuration is manipulated by varying the capability tier
of models on the parallel chains and by varying whether the synthesis
node receives an explicit capability disclosure label. The
implicit-versus-standard contrast isolates capability asymmetry; the
declared-versus-implicit contrast isolates capability disclosure on top
of asymmetry.

**Hierarchical Structures**

The third class comprises the directed hierarchy and the ring with
shortcuts. Both structures introduce structural asymmetry, specifically
positional differences that create systematic variation in the
processing history of information at any given node. They differ in
the character of that asymmetry: in the directed hierarchy, asymmetry
is explicit and tier-ordered (upper-tier nodes\' outputs constrain
lower-tier processing, creating a top-down cascade); in the ring with
shortcuts, asymmetry is path-length-based (messages arriving via
shortcuts have traversed fewer hops than messages traversing the ring,
creating within-network fidelity heterogeneity without a structural
ordering of nodes).

The directed hierarchy is selected because it describes a major class of
tiered AI deployment architectures, including command-and-control AI
systems, clinical protocol cascades, and content production pipelines
with strategy, creation, and distribution tiers, and because its
structurally tiered cascade provides a direct test of how positional
capability placement shapes information mutation across tiers when the
hierarchy is *capability-ordered* (the manipulated high-capability
condition). Capability placement is manipulated within the directed
hierarchy by varying whether upper-tier nodes are higher-capability or
standard models, testing whether the cascade amplification of upper-tier
text properties differs by capability level. The ring with shortcuts is
selected as the distributed, non-hierarchical comparison case,
representing federated AI learning networks, distributed moderation
systems, and peer AI networks without a structurally privileged
position, and provides a test of how path-length heterogeneity shapes
fidelity distributions. The capability configuration is not manipulated
in the ring-with-shortcuts condition, as the structure has no
structurally privileged node and no synthesis decisions; its inclusion
tests the structural effects of distributed, non-hierarchical routing
without the confound of capability asymmetry.

**Hypotheses**

Our hypotheses are organized around three empirically separable
mutation types in M2M transmission chains. We define each as follows
and use these definitions consistently throughout the manuscript:

- *Drift*: cumulative semantic movement along a lineage.
- *Divergence*: between-lineage dispersion among independent transmissions from the same seed.
- *Fabrication*: addition of content or epistemic commitments not traceable to the source.

These mutation types have different structural origins and respond to
different network properties, making topology the primary theoretical
lever. We use *mutation* rather than *error* when making the
taxonomic claim, since drift in particular can include benign
paraphrase that does not impair meaning; we reserve *error* for cases
where impairment is empirically demonstrated, as in the impairment-
bearing dependent variables (hallucination, completeness loss,
fidelity loss).

**Network Topology and Fabrication: Two Mechanisms**

Fabrication in M2M networks does not have a single source. We
distinguish two mechanisms through which topology can produce
content untraceable to a node\'s inputs.

*Synthesis fabrication* occurs at multi-input nodes, where competing
inputs must be reconciled into a single output. The synthesis node
generates a coherent resolution that is not entailed by any of its
individual inputs—a confident declarative produced by reconciling
divergence. Synthesis structures (lattice and bidirectional lattice)
concentrate this kind of fabrication, and so do hub-and-spoke and
directed hierarchy structures wherever the architecture requires
multi-input integration.

*Sequential reconstruction fabrication* occurs at single-input nodes,
where a node repeatedly paraphrases or summarizes ambiguous, anomalous,
or schema-inconsistent material. Across many hops, model priors fill
gaps, regularize uncertainty, and impose coherence-consistent structure
that the original material did not contain. Linear chains, with their
long single-input sequences and absence of countervailing inputs, are
the canonical site for this mechanism. The fabrication is not produced
by reconciliation; it accumulates through cumulative reconstruction
under the model\'s distributional priors.

Topology should therefore predict fabrication through *both*
mechanisms: synthesis structures should elevate fabrication where
inputs diverge, and linear chains should elevate fabrication when
content is narratively complex, ambiguous, or schema-inconsistent.
Hierarchical structures, with capability-ordered constraints that bound
what each tier can plausibly produce, should minimize fabrication
across both mechanisms.

**H1:** Network topology will predict hallucination rates through two
mechanisms—synthesis fabrication at multi-input nodes and sequential
reconstruction fabrication at single-input nodes. Hierarchical
structures (hub-and-spoke, directed hierarchy), which constrain both
mechanisms, will produce the lowest fabrication; bidirectional lattice
structures, which maximize unconstrained synthesis through iterative
back-communication, will produce high fabrication; linear chains will
produce high absolute fabrication when content is narratively complex,
even though they contain no synthesis nodes.

**Cross-Lineage Divergence**

Cross-lineage divergence, the degree to which independent lineages
of the same condition arrive at different final outputs, reflects how
much variance a network structure introduces across runs. Centralized
structures route all processing through a single node, homogenizing
outputs. Distributed synthesis structures allow independent chains to
develop in parallel before reconciliation, amplifying divergence. The
hub, which funnels all information through one node before fan-out,
should produce near-zero divergence. The bidirectional lattice, which
develops two independent chains before iterative synthesis, should
produce the most.

**H2:** Network topology will predict cross-lineage divergence (XL-SD).
Centralized structures (hub, directed hierarchy) will produce lower
divergence than distributed synthesis structures (bidirectional lattice,
lattice), with sequential structures (linear, ring) occupying an
intermediate position.

**Capability Placement, Capability Asymmetry, and Fabrication**

The structural amplification logic of hub-and-spoke and hierarchical
networks means that a higher-capability model at the hub or upper tier
does not merely improve local output quality. Its processing reaches
every downstream node in the network. We predict that this
amplification makes *capability placement* at structurally consequential
positions a system-level rather than local-level intervention, reducing
fabrication throughout the network rather than only at the upgraded
node itself. *Capability asymmetry* in lattice and bidirectional
lattice configurations is conceptually adjacent but structurally
weaker: the upgraded model is on a parallel input chain rather than at
a single amplified node, and its downstream reach is bounded by the
single synthesis decision that follows. We therefore expect smaller
asymmetry effects on fabrication than placement effects.

**H3 (capability placement and asymmetry):** Higher-capability models
at structurally consequential positions will reduce fabrication
relative to standard-capability configurations. The effect should be
strongest under capability placement (hub, hierarchy), where the
upgraded node\'s outputs propagate to many downstream nodes, and
smaller under capability asymmetry (lattice, bilattice), where
upgraded-chain outputs feed into a single synthesis decision.

**Capability Disclosure**

In synthesis topologies (lattice and bidirectional lattice), capability
disclosure can be manipulated independently of capability asymmetry by
varying whether the synthesis node receives an explicit label
indicating that one input came from a higher-capability system. Whether
the label additionally moves synthesis outcomes beyond what input
properties alone produce is the empirical question. A reliable
declared-label effect would indicate status-like source-cue weighting; a
null effect would indicate that mutation is governed primarily by
generated content and structural configuration rather than by explicit
status signaling. We frame this as a mechanism contrast, not as a
demonstration of authority.

**H4 (capability disclosure):** Capability disclosure will not improve
information quality beyond capability asymmetry. If synthesis nodes
respond primarily to the semantic properties of inputs rather than to
explicit source labels, declared and implicit capability conditions will
produce statistically indistinguishable outcomes.

**Content Complexity**

Network topology's protective and amplifying effects on fabrication
depend in part on the content being transmitted. Routine organizational
content provides synthesis nodes with clear, low-ambiguity inputs that
constrain reconciliation decisions. Narratively complex or
schema-inconsistent content, such as cultural narratives with
unfamiliar elements, provides more ambiguous inputs, creating greater
opportunity for fabrication as nodes generate schema-consistent
resolutions that neither input contained. We predict that this
interaction between content complexity and topology will be visible in
the relative magnitude of topology effects across content types.

**H5:** The effect of network topology on hallucination will be larger
for narratively complex content (War of the Ghosts stimulus) than for
organizational content, as the structural protections and amplifications
of different topologies are more consequential when inputs are ambiguous
or schema-inconsistent.

**Compounding Effects**

Topology differences in information quality are not static across
transmission chains: they compound as information traverses additional
nodes. Early-hop differences may be small, but each transmission step
multiplies prior differences, meaning that terminal outputs, the
information a decision-maker actually receives, should show
substantially larger topology effects than intermediate outputs. This
compounding prediction carries practical weight: evaluations of M2M
system quality that measure only intermediate nodes will systematically
underestimate the magnitude of topology effects at the point of use.

**H6:** Topology effects on information quality will be larger at
terminal nodes (final hop) than at intermediate positions, as structural
differences in error accumulation compound across the transmission
chain.

**Capability Configuration and Divergence**

The finding that topology strongly predicts cross-lineage divergence
(H2) raises a natural follow-on question: can placing higher-capability
models at structurally consequential positions reduce the divergence
that architecture produces? The intuition is plausible—better models
might generate more consistent outputs across parallel runs, compressing
the variance that distributed synthesis structures introduce—but we
predict it is incorrect.

**H7:** Capability condition will not reduce cross-lineage divergence
once topology is controlled. Divergence is expected to be an
architectural property of branching and synthesis structure rather than
a local capability property of individual nodes. Upgrading model
capability at any structural position will not meaningfully reduce
inconsistency across parallel lineages; architectural redesign is the
only effective intervention.

*Note on factual retention as a dependent variable.* We do not
formulate a separate hypothesis for factual retention. Inspection of
the data suggested early on that factual retention behaves very
differently from the other DVs and merits its own treatment in the
Results section as a distinct phenomenon, rather than being framed as a
test of topology effects. We return to it in a dedicated Results
subsection below.

**Methods**

We examine information mutation across six M2M network topologies using
a fully synthetic experimental pipeline in which LLM agents serve as
both network nodes (transmitting and transforming messages) and semantic
coders (rating the similarity of transmitted messages to their
originals). Seven seed sentences serve as stimuli: six organizational
seeds spanning four content categories (factual, normative, narrative,
procedural) designed for the primary hypothesis tests, and one adapted
from Bartlett\'s (1932) classic War of the Ghosts stimulus, included as
an exploratory extension examining whether M2M transmission produces the
schema-driven distortion patterns documented in human serial
reproduction research. This approach departs from the human-subject
methodology of Brashears and Gladstone (2016). To our knowledge, the
synthetic-pipeline approach has not previously been used for systematic
topology-comparative study of information diffusion at this range of
architectures, although the LLM landscape is moving quickly enough that
any firstness claim should be read narrowly. The choice of synthetic agents is not merely a
methodological convenience: it directly enacts the theoretical
phenomenon under study. We are examining how networks of AI agents
mutate information; using AI agents to constitute those networks is
internally consistent in a way that human subject studies of M2M
dynamics are not.

The pipeline was developed through an iterative
calibration process. Preliminary analyses confirmed that LLM agents
serving as active mediation nodes (paraphrasing for meaning) produce the
predicted diversification signature, specifically higher cross-lineage semantic
variance than passive relay nodes, in linear chain configurations.
We discuss both the capabilities and the known limitations of the
synthetic approach in detail below.

**Transmission Nodes**

Two node types are implemented in the pipeline, corresponding to the
theoretical distinction between active and passive mediation. Passive
relay nodes receive a message and reproduce it with minimal
transformation, modeling AI agents that function primarily as conduits
(forwarding, routing, or lightly reformatting) without substantial
semantic reprocessing. Active mediation nodes receive a message and
paraphrase it for meaning, modeling AI agents that interpret, summarize,
reformulate, or otherwise substantially process the semantic content of
the message before passing it forward. This is the functionally relevant
distinction for M2M information mutation: passive relay introduces only
channel-level noise (minimal in well-designed AI systems), while active
mediation introduces the transformation-level mutations that are the
subject of this study.

All transmission nodes use the Claude Haiku 4.5 model (Anthropic, 2025).
The choice of a single, consistent model for transmission nodes in the
baseline conditions controls for model-specific effects, allowing
topology effects to emerge cleanly. In capability-manipulation
conditions, we vary the model at designated nodes between frontier-class
(Claude Sonnet 4.6) and standard-class (Claude Haiku 4.5). This
operationalizes capability tier as the basis for differential weighting
of machine outputs—the most theoretically grounded and practically
relevant basis available to a study of this scope.

The operationalization differs by structural class. For Class I
(hub-and-spoke) and Class III (directed hierarchy), the manipulation is
*capability placement*: the higher-capability model occupies a single
structurally consequential node (hub or upper tier), and no explicit
signal is provided to any downstream node because the topology contains
no competing inputs at which a label would be operative. For Class II
(lattice and bidirectional lattice), the manipulation operates as
*capability asymmetry* between parallel chains, and we further separate
asymmetry from capability disclosure by implementing two conditions. In
the *implicit* condition, Chain A is processed by the higher-capability
model and Chain B by the standard-capability model, but the synthesis
node receives no information about this asymmetry. It receives two
texts and must synthesize them without provenance metadata. This
condition isolates capability asymmetry: any movement relative to the
standard condition reflects the influence of upstream text quality
alone. In the *declared* condition, the setup is identical but the
synthesis node\'s prompt additionally includes the notation: "Note:
Version A was processed by a higher-capability system." The
declared-versus-implicit contrast isolates capability disclosure on top
of asymmetry: any movement reflects the influence of the explicit
label beyond what input properties alone produce. The standard
condition, in which both chains use the same model and the synthesis
node receives no signal, provides the baseline for both contrasts.

For active mediation nodes, the transmission prompt instructs the model
to read the received message carefully and write a new sentence
capturing the intended meaning, in the same message format as received.
For passive relay nodes, the prompt instructs the model to reproduce the
received message as accurately as possible. Both prompts are held
constant across all topology conditions; the only variation is the node
type designation and, in capability-manipulation conditions, the model
assigned to the node.

**Semantic Coding**

Semantic similarity between transmitted messages and their progenitors
is assessed using Claude Sonnet 4.6 as the coder instrument. For each
sentence pair, the coder is prompted to rate the similarity of the two
sentences\' meanings on a 0-100 scale (0 = completely different
meanings; 100 = identical meanings), ignoring surface differences in
spelling, grammar, and format. Three coding repetitions are conducted
per pair, and the mean score is taken as the fidelity measure. The use
of a near-zero temperature setting (0.10) for the coder produces high
within-pair reliability across repetitions.

The coder is treated as a consistent measurement instrument for the LLM
system under study rather than as a proxy for human judgment. All
inferences in this study are within-instrument and
topology-comparative: every condition is scored by the same coder under
identical prompts and parameters, so any systematic biases in the coder's
absolute ratings affect all conditions equally and do not confound
relative differences across topologies. We therefore refrain from
claims about absolute fidelity values and restrict interpretation to
comparative effects across topology and capability conditions.

**Seed Sentences**

Seven seed sentences serve as the starting points for all diffusion
chains. Six are designed specifically for this study to ensure coverage
of the content types most prevalent in organizational M2M communication
and to enable measurement of all seven dependent variables. The seventh
is adapted from Bartlett\'s (1932) classic serial reproduction stimulus,
\"The War of the Ghosts,\" included as a deliberate methodological
bridge to the foundational social psychological literature on human
information transmission.

The six organizational seeds are organized into four content categories
(factual, normative, narrative, and procedural) with two complex
seeds that combine categories, reflecting the mixed-type content typical
of real organizational communication. All organizational seeds range
from 45 to 65 words, providing sufficient semantic richness for active
mediation to produce meaningfully different paraphrases while remaining
processable by all transmission models. Each contains at least three
distinct factual markers (specific numbers, named entities, precise
claims, or temporal references) whose survival through the diffusion
chain is tracked for factual retention analysis.

***War of the Ghosts***

Bartlett\'s (1932) serial reproduction studies established the
foundational framework for understanding how human memory reconstructs
rather than reproduces information during transmission. Using \"The War
of the Ghosts,\" a Native American folk tale culturally foreign to his
British participants, Bartlett documented three systematic patterns of
distortion in human serial reproduction chains: assimilation (details
altered to fit cultural schemas), leveling (omission of information
deemed unimportant, producing shorter retellings with each
transmission), and sharpening (reordering of events to produce
culturally familiar narrative structure). These patterns were not random. They reflected the operation of prior knowledge structures, or
schemas, on reconstructive memory. The story was chosen by Bartlett
precisely because its cultural foreignness to British participants
maximized schema-driven distortion, making the reconstructive nature of
memory visible.

The relevance of this stimulus to M2M transmission research is direct
and theoretically generative. LLMs process information through learned
statistical patterns in training data rather than through cultural
schemas in the human sense, yet they are not schema-free. LLMs have
systematic biases toward certain narrative structures, registers, and
semantic patterns that reflect their training distributions. These
biases may function analogously to schemas, producing systematic rather
than random transformation of culturally anomalous content. Whether M2M
transmission of the War of the Ghosts produces Bartlett-type patterns
(assimilation toward culturally coherent narrative, leveling of
anomalous detail, sharpening of causal structure) or produces
categorically different transformation patterns is an open question with
direct theoretical implications for understanding the similarities and
differences between human and machine information processing.

*Recent work* using the serial reproduction method with human
participants has confirmed and extended Bartlett\'s findings. Ost et al.
(2022) showed that recall of the War of the Ghosts was significantly
worse over serial reproduction chains than recall of a culturally
familiar urban myth, supporting Bartlett\'s prediction that
schema-inconsistent material is most vulnerable to transmission
distortion. The cultural attraction theory framework developed by
Sperber (1985) and applied to LLM chains by Yax et al. (2025) predicts
that iterative transmission should produce convergence toward attractor
states, stable forms toward which transformation tends regardless of
starting conditions. Whether the War of the Ghosts has the same
attractor in LLM chains as in human chains, or whether LLM attractors
differ systematically from human ones, is the question this seed is
designed to address.

We include a condensed version of the stimulus that preserves the key
schema-violating elements Bartlett identified as diagnostically
important: causally unmotivated participation, the ambiguous death
mechanism, and the culturally anomalous phrasing. The condensed version
is adapted to be processable within our chain structure while retaining
the essential properties of the original:

*Seed 7 (Bartlett stimulus, adapted from Bartlett, 1932):* One night
two young men from Egulac went down to the river to hunt seals. They
heard war-cries and a canoe with five warriors appeared. One young man
agreed to join the fight though he could not understand why. In the
battle he was not hurt, though many died around him. Later he told the
people of Egulac what had happened. When the sun rose he fell down, and
something black came out of his mouth. He was dead.

Analysis of Seed 7 is conducted separately from the organizational seeds
and is treated as an exploratory comparison rather than a primary
hypothesis test. We examine whether the three Bartlett distortion
patterns (assimilation, leveling, and sharpening) are detectable
in M2M transmission chains, and whether active mediation nodes produce
more or less schema-consistent distortion than passive relay nodes. We
additionally examine whether the transformation profile of Seed 7 in M2M
chains resembles or departs from the human serial reproduction results
documented by Bartlett (1932) and Ost et al. (2022), using the latter as
a qualitative benchmark. Coding of Bartlett-type distortion patterns is
conducted via additional LLM coding passes assessing whether transmitted
versions are shorter than their inputs (leveling), whether anomalous
elements have been replaced with culturally coherent alternatives
(assimilation), and whether causal structure has been made more explicit
(sharpening).

***Organizational Seeds***

The six organizational seeds are as follows:

*Seed 1 (Factual):* A 2024 audit of the regional supply chain identified
14 critical vulnerabilities across three distribution hubs, with the
highest concentration in cold storage facilities operating below the
mandated 34-degree Fahrenheit threshold. The audit estimated that
unaddressed vulnerabilities would increase spoilage losses by
approximately 23 percent annually, at a projected cost of \$4.2 million
to the consortium.

*Seed 2 (Normative):* The ethics review committee concluded that the
proposed clinical trial protocol presents unacceptable risks to
vulnerable populations and should not proceed without substantial
revision. The committee noted particular concern about the inadequacy of
the informed consent procedures and the absence of independent safety
monitoring, both of which fall below established standards for research
involving older adult participants with mild cognitive decline.

*Seed 3 (Narrative):* When the lead researcher noticed the anomalous
readings at 11:47 PM on a Tuesday, she initially attributed them to
sensor calibration drift. It was only after cross-referencing three
weeks of archived data that the pattern became clear: the facility had
been leaking trace amounts of a regulated compound into the groundwater
since the previous March, undetected by the automated monitoring system.

*Seed 4 (Procedural):* To initiate the data recovery protocol, the
on-call engineer must first isolate the affected partition by disabling
write access, then notify the security team before attempting any
restoration. Recovery should proceed only from backups created within
the previous 72 hours, and all actions must be logged in the incident
management system before the engineer completes the incident record.

*Seed 5 (Complex: Factual-Narrative):* Between January and September of
last year, the three largest hospital networks in the region reported a
combined 340 cases of a rare post-surgical complication, representing a
280 percent increase over the same period the prior year. Investigators
tracing the pattern eventually identified a common thread: all affected
patients had received a specific lot of surgical mesh manufactured by a
single supplier, which had passed all required quality inspections.

*Seed 6 (Complex: Normative-Procedural):* The board\'s policy requires
that any AI-generated recommendation affecting more than 500 employees
must be reviewed by at least two senior managers before implementation,
and that the reviewing managers must document their independent
assessments before comparing notes. This requirement exists specifically
to prevent anchoring effects in high-stakes decisions, and exceptions
may be granted only by the chief executive with written justification.

Seed category is treated as a moderating variable in the analysis of the
six organizational seeds. Primary hypotheses are tested across all six;
post-hoc analyses examine whether topology and authority effects are
moderated by seed category. We expect factual seeds to be most sensitive
to path-length effects, normative seeds to be most sensitive to active
mediation effects, procedural seeds to be most sensitive to synthesis
conditions, and complex seeds to exhibit the highest overall
vulnerability across all conditions. Analysis of Seed 7 is conducted
separately and reported as an exploratory extension.

**Dependent Variables**

**Consecutive fidelity** is the mean LLM-coded semantic similarity of
each transmitted sentence to its immediate predecessor in the chain. It
measures the rate of semantic change at each transmission step and
provides a chain-level diagnostic for detecting positions where major
mutations occur.

**Evolutionary fidelity** is the mean LLM-coded semantic similarity of
each transmitted sentence to the original seed sentence. It measures
cumulative semantic degradation from the origin and is the primary
measure of information preservation across the full chain.

**Cross-lineage standard deviation of evolutionary fidelity** is
computed across lineages sharing the same seed sentence and topology
condition, at each chain position. High cross-lineage SD indicates that
different lineages have diverged substantially in their semantic
distance from the original seed. This is the diversification signature.
Computing this at every hop rather than only at chain termination allows
characterization of the diversification trajectory: when lineages
diverge, and whether that divergence accelerates, decelerates, or occurs
as discrete jumps.

**Factual retention** is the proportion of factual markers present in
the seed sentence that survive intact in the transmitted sentence.
Factual markers include specific numbers, proper names, and precise
claims that can be identified in transmitted sentences by LLM-coded
binary assessment (present or absent). This measure captures a dimension
of information loss not captured by semantic similarity: a transmission
may preserve the gist of a message while omitting its specific factual
content, with potentially severe consequences for decision-making
quality in organizational contexts.

**Information completeness** is the proportion of semantic content units
present in the seed sentence that are preserved in the transmitted
sentence, assessed by LLM coding of each transmission against its seed.
Completeness differs from evolutionary fidelity in that it measures what
was retained rather than how similar what was retained is to the
original: a short, accurate summary may score high on fidelity but low
on completeness, while a lengthy but accurate elaboration may score high
on both.

**Hallucination** is a 0–100 LLM-coded measure of *added* factual
content present in the transmitted sentence but absent from the
original seed. The coder (Claude Sonnet 4.6, temperature 0.10) is
prompted to rate the degree to which the transmission contains specific
details, claims, or facts that are not present in the original, with
explicit instruction that "paraphrase and synonym substitution alone do
not count as hallucination" and that the relevant added content
includes "numbers, names, dates, causal claims, events." A score of 0
indicates that everything stated in the transmission can be found in
the original; a score of 100 indicates that the transmission contains
many fabricated details absent from the original. Several features of
this operationalization warrant explicit note. (a) The coder compares
each transmission to the *original seed*, not to the immediate
predecessor or the full chain history. The score therefore reflects
distance from origin in the dimension of added content. (b) Omissions
are not scored here; loss of original content is captured by factual
retention and information completeness. (c) Causal inferences not
present in the original are scored as hallucination, as are temporal
restructurings that introduce events not in the original. (d) Paraphrases
and stylistic substitutions are not penalized. (e) Examples are not
included in the hallucination prompt; the coder is given only the
definition, the seed, and the transmission. (f) A sentence can score
high on hallucination while preserving most or all of the seed\'s
factual markers, because hallucination measures additions and factual
retention measures survival of seed-side anchors. The two are
empirically dissociable, and we treat them as measuring distinct
computational phenomena.

We define *epistemic-status fabrication* as a subtype of hallucination
in which factual markers are preserved but their evidentiary status is
altered—a projection becomes a stated fact, a conditional becomes a
declarative, an estimate becomes a realized outcome. The illustrative
spoilage example below is a paradigm case: numbers and entities survive
intact while "would increase... at a projected cost" is replaced by
"have resulted in... costing." The hallucination prompt scores such
shifts because the new modal claim is added factual content not present
in the original.

**Semantic drift direction** measures the direction of semantic
transformation across the chain, assessed along two dimensions: register
(formal versus informal, assessed by LLM rating on a 0-100 scale) and
specificity (specific versus general, assessed similarly). Drift
direction captures the systematic biases in LLM transformation that
fidelity measures cannot: whether chains consistently drift toward
formality, abstraction, or particular topical framings. These are the attractor
dynamics identified in the cultural attraction theory literature
(Sperber, 1985; Yax et al., 2025).

**Higher-capability content incorporation rate** is computed in
capability-manipulation conditions across all three topology classes.
At each synthesis node (Class II) or designated upgraded-node position
(Class I hub and Class III hierarchy), we assess the semantic
similarity of the node\'s output to each of its inputs and classify the
output as reflecting the higher-capability model\'s semantic content,
the standard-capability model\'s semantic content, or a blend, based on
relative similarity scores. The incorporation rate is the proportion
of decisions in which the higher-capability model\'s semantic content
prevails. We deliberately use the descriptive term *content
incorporation* rather than *adoption* or *deference*: semantic
similarity to one input does not by itself demonstrate status-like
weighting. In the implicit condition, incorporation may reflect upstream
text quality alone; only the declared-versus-implicit contrast
separates label-driven incorporation from quality-driven incorporation,
and only the latter contrast is a test of the *authority-like adoption*
mechanism developed in the theory section.

**Design**

All transmission nodes use active mediation throughout the study.
Preliminary calibration established that passive relay nodes produce
near-ceiling fidelity (evol_fidelity ≈ 100) regardless of topology or
capability condition, offering no variance for analysis. All messages
are transmitted in standard English; as M2M pipelines built on large
language models operate in natural language by design, English is the
ecologically valid format for this context.

The study comprises twelve experimental conditions defined by the
crossing of topology and capability configuration. Four topologies have
a single capability condition (linear chain: standard; ring: standard),
and four have multiple (hub-and-spoke: standard vs. high-capability hub;
lattice: standard vs. implicit vs. declared; bidirectional lattice:
standard vs. implicit vs. declared; directed hierarchy: standard vs.
high-capability upper tier). All twelve conditions are run for all seven
seed sentences. Five independent lineages are run per condition per seed
sentence, yielding 420 chains and 5,880 node-level observations in
total. The chain is the independent replication unit (n = 420); the
5,880 figure refers to the total node-level observations and is reported
descriptively. Cross-lineage divergence is computed at the
condition-by-seed cell level (n = 70 cells across topology × capability
× seed). Each lineage is an independent replication of the full
diffusion process from the same seed under the same conditions, allowing
computation of cross-lineage variance (XL-SD) at every hop.

Chain length is equalized at 11 nodes across all six topologies,
implemented as follows: linear chain, 11 sequential nodes; hub-and-spoke,
1 hub node plus 10 downstream spoke nodes; lattice, two parallel chains
of 5 nodes each converging at 1 synthesis node; bidirectional lattice,
same parallel structure with back-communication enabled between chains
for a maximum of 3 iterative rounds before the synthesis node produces
final output; directed hierarchy, 3 upper-tier nodes feeding 5
mid-tier nodes feeding 3 lower-tier terminal nodes; ring with shortcuts,
11 nodes in a closed ring with 3 shortcut edges connecting non-adjacent
nodes. Equalizing node count blocks a crude node-count confound, but
the topologies still differ on a bundle of correlated properties
(number of transformation events, number of synthesis events,
distribution of path lengths, whether outputs are merged or forwarded).
Topology should therefore be understood as an architectural bundle
rather than a pure graph-theoretic property isolated from processing
differences.

Capability configuration is manipulated within applicable topologies.
For hub-and-spoke and directed hierarchy, the manipulation is
capability placement: the hub or upper-tier nodes are assigned either
the higher-capability model (Claude Sonnet 4.6) or the
standard-capability model (Claude Haiku 4.5). For lattice and
bidirectional lattice, three conditions are compared: *standard* (both
chains use the same model, no signal); *implicit* (Chain A uses the
higher-capability model, Chain B the standard model, synthesis node
receives no provenance information); *declared* (same model asymmetry,
synthesis node prompt additionally includes: "Note: Version A was
processed by a higher-capability system"). The implicit-versus-standard
contrast isolates capability asymmetry; the declared-versus-implicit
contrast isolates capability disclosure on top of asymmetry. All other
parameters are held constant across conditions.

**Measurement Examples: Three Error Types**

The dependent variables described above target three qualitatively
distinct mutation patterns. We define each pattern with a worked example
drawn from the study data, both to make the measures concrete and to
anchor the analyses that follow. These examples are not merely
illustrative; they delimit what counts as drift, fabrication, and
synthesis-driven assimilation in the analyses below.

*Drift: Sequential accumulation in a linear chain (Seed 2, Normative,
linear chain, standard condition).* The seed reads: "The ethics review
committee concluded that the proposed clinical trial protocol presents
unacceptable risks to vulnerable populations and should not proceed
without substantial revision. The committee noted particular concern
about the inadequacy of the informed consent procedures and the absence
of independent safety monitoring, both of which fall below established
standards for research involving older adult participants with mild
cognitive decline." This seed is stable across 11 hops (evol_fidelity
= 97 at hops 1 and 11), with each node producing a faithful paraphrase.
"Concluded" and "determined" alternate across hops; "cannot proceed
without substantial revision" and "cannot move forward unless
substantially revised" appear as semantically equivalent variants. No
substantive content is added or lost. This is the baseline drift
pattern for routine organizational content in sequential chains: meaning
is preserved, but word-choice shifts accumulate silently. These shifts
are individually trivial but compound over longer chains and more
complex seeds.

*Fabrication: Synthesis distortion in a bidirectional lattice (Seed 1,
Factual, bidirectional lattice, standard condition, synthesis node).*
The seed reads: "A 2024 audit of the regional supply chain identified
14 critical vulnerabilities across three distribution hubs... The audit
estimated that unaddressed vulnerabilities would increase spoilage losses
by approximately 23 percent annually, at a projected cost of $4.2
million to the consortium." The synthesis node, having received two
slightly different parallel versions, produced: "These vulnerabilities
have resulted in a 23 percent rise in annual spoilage losses, costing
the consortium approximately $4.2 million yearly." The numbers survive
intact. What is fabricated is the epistemic status: the original's
conditional projection ("would increase... at a projected cost") has
been converted to a stated present fact ("have resulted in... costing").
The synthesis node resolved ambiguity between its two inputs by
generating a confident declarative that neither input contained.
A decision-maker reading the terminal output would act on a concluded
fact rather than an estimate. Hallucination score: 100.

*Compounding fabrication and assimilation: Bartlett stimulus in a
bidirectional lattice (Seed 7, War of the Ghosts, bidirectional
lattice, standard condition).* The seed's most schema-violating
elements ("he could not understand why," "something black came out
of his mouth," "He was dead") survive to hop 3 (evol_fidelity = 96,
hallucination = 12). By the hop 5.5 synthesis node, both chains have
lost the death mechanism entirely; the synthesis node introduces "felt
compelled to join the battle" and "felt an inexplicable urge to
participate." Neither phrase appears in any prior transmission.
By hop 11, the transmitted text reads: "Two young men from Egulac
departed at night to hunt seals along the river. They came upon a canoe
containing five warriors engaged in combat. One of the young men felt
drawn to participate in the battle. He fought throughout the entire
conflict and survived..." Evol_fidelity = 72, hallucination = 100.
The culturally anomalous ending has been replaced by a schema-consistent
survival narrative generated by the synthesis node. This is assimilation
in the Bartlett sense, but its mechanism here is synthesis fabrication
rather than individual memory reconstruction.

These three examples illustrate the qualitative character of the three
mutation types and motivate the quantitative analyses that follow. A
crucial observation across all three: hallucination scores of 100 do
not indicate obviously wrong or incoherent text. The transmitted
versions are fluent, internally consistent, and in many cases more
readable than the originals. The fabrication is silent, confident, and
undetectable without access to the original seed.

**Analytic Strategy**

Dependent variables were examined for distributional properties prior
to analysis. Evolutionary fidelity and completeness are approximately
normally distributed with left skew; consecutive fidelity is similar.
Hallucination scores are zero-inflated and heavily right-skewed (27%
zeros; mean = 10.2, SD ≈ 25), violating the assumptions of ordinary
least-squares regression. Non-parametric methods are used throughout
for significance testing.

The dataset is hierarchically structured: each of the 5,880 node-level
observations is nested within one of 420 chains, which are nested
within 70 condition-by-seed cells (12 capability-by-topology conditions
× 7 seeds, with cell counts varying by chain length). Although the
node-level total is reported descriptively, the independent replication
unit is the chain (n = 420), and cross-lineage divergence is analyzed
at the cell level. We use this nested structure to inform the choice of
analysis at each step.

Main effects of topology on each dependent variable are evaluated using
Kruskal-Wallis tests with pairwise post-hoc comparisons applying
Bonferroni correction (α = .05 / number of pairs). Effect sizes are
reported as rank-biserial correlation coefficients (r_rb) for pairwise
comparisons and η² for omnibus tests (η² = (H − k + 1) / (n − k), where
H is the Kruskal-Wallis statistic, k is the number of groups, and n is
the total sample size). We acknowledge that node-level Kruskal-Wallis
tests treat within-chain observations as independent and therefore
overstate effective n; we treat the resulting *p*-values as descriptive
rather than as exact inferential statements, and rely primarily on
effect sizes (η², r_rb) and chain- and cell-level summaries when
interpreting results.

Capability-condition effects within topology are evaluated using
Mann-Whitney U tests (two-condition comparisons: hub, hierarchy) or
Kruskal-Wallis with pairwise post-hoc (three-condition comparisons:
lattice, bilattice).

Cross-lineage divergence (XL-SD) is computed for each (topology ×
capability × seed) cell as the standard deviation of evol_fidelity
across the five lineages at the terminal hop. Topology effects on XL-SD
are evaluated using Kruskal-Wallis at the cell level (where the unit of
analysis is the cell, not the node); capability-condition effects are
evaluated via OLS regression (XL-SD ~ topology + capability) to allow
simultaneous estimation of both predictors.

Hop trajectory analyses model evol_fidelity as a function of hop number
(continuous, with squared term) within topology, characterizing whether
degradation is linear, accelerating, or decelerating across the chain.
Terminal-node (final-hop) analyses are conducted separately using only
the maximum-hop observation per chain, providing the practically
relevant estimate of topology effects on the output a decision-maker
would receive and the analysis at which the chain (rather than the
node) is the unit.

Seed type moderation is evaluated by comparing topology and
capability-condition effect sizes within organizational seeds (seeds
1--6) versus the Bartlett stimulus (seed 7), using Mann-Whitney U with
rank-biserial correlation. Topology × seed type interactions are
reported where the Bartlett effect size exceeds that for organizational
seeds.

All analyses are within-instrument: comparisons are made between
topology and capability conditions using the same LLM coder throughout,
rendering coder-level biases a constant that does not affect
topology-comparative inferences. Seed sentence is included as a fixed
effect in all regression models. Significance threshold is α = .05
with Bonferroni corrections applied for multiple comparisons within
each hypothesis test.

Because node-level observations are nested within chains and seeds, we
also estimated mixed-effects robustness models for the primary node-level
outcomes. Evolutionary fidelity and completeness were modeled using
linear mixed-effects models with random intercepts for chain (run) and
fixed effects for topology, hop, hop squared, capability configuration,
and seed type, including a topology × hop interaction. Hallucination was
modeled using a two-part specification: a generalized estimating
equations (GEE) logistic model predicting any hallucination (hallu > 0)
clustered by chain, and a positive-only linear mixed-effects model
predicting log-transformed hallucination severity. Cross-lineage
divergence and chain-level terminal outcomes were modeled with OLS or
GLM at the cell or chain level, where unit-of-analysis concerns about
within-chain dependence do not apply. These models are reported in
Appendix A as robustness checks rather than replacements for the
non-parametric analyses, which remain the primary descriptive
comparisons given the bounded and skewed dependent variables. The
robustness models confirm the substantive pattern reported in the main
text; we discuss specific divergences in the appendix.

**Synthetic Pipeline**

The use of a fully synthetic LLM pipeline to study M2M information
diffusion represents a methodological departure from previous work in
this tradition and merits explicit discussion. Three concerns deserve
direct address.

First, the concern that synthetic agents do not faithfully represent the
real M2M systems under study. We make no claim that our pipeline
precisely replicates any specific organizational AI deployment. Our
claim is that the pipeline instantiates the theoretically relevant
properties of M2M networks (sequential and synthesis processing by
LLM agents, with topology manipulated as the independent variable) in
a controlled and reproducible way. The pipeline is a model of M2M
communication, not an ethnography of a specific system. As with all
experimental models, its value lies in the controlled variation it
enables, not in its surface fidelity to any particular real-world
context.

Second, the concern that the semantic coder is itself an LLM and
therefore inherits whatever systematic biases characterize that family
of models. We concede this directly and make no claims about absolute
fidelity values. All comparisons in the present study are
within-instrument: every topology and capability condition is scored by
the same coder under identical prompts and parameters, so any
systematic bias in the coder is a constant across conditions and does
not confound inference about relative differences. The appropriate
interpretive frame is therefore comparative: how does information
mutate more or less, or in different ways, across topologies, not what
is the true absolute fidelity of any particular condition. Within-
instrument comparison does not, however, fully neutralize the concern.
A coder bias that interacts with topology, content type, or text style
could in principle inflate or deflate condition contrasts. We address
this risk through within-instrument comparison alone in the present
study, treat findings about absolute magnitudes with corresponding
caution, and flag the boundary in the limitations section.

Third, the concern that the choice of a specific LLM (Claude Haiku 4.5
for transmission, Claude Sonnet 4.6 for coding) limits the
generalizability of findings. We treat model choice as a design
parameter, not a nuisance, and we explicitly manipulate it in
capability-placement conditions. Findings about topology effects are
most directly generalizable to M2M systems using models of similar
capability profiles; findings about capability placement and capability
disclosure are specifically about capability-tier asymmetry between
frontier-class and standard-class models within the Claude family.
Future work should examine whether topology effects replicate across
different model families and generations, a question our infrastructure
is well-positioned to address.

**Results**

The full dataset comprises 5,880 observations across 420 chains (12
conditions × 7 seeds × 5 lineages), with each chain traversing 11
nodes. Results are organized by hypothesis. Descriptive statistics for
all dependent variables by condition are presented in Table 1.
Statistical tests use non-parametric methods throughout given the
zero-inflated, right-skewed distribution of hallucination scores (27%
zeros; mean = 10.2, SD = 24.8); evolutionary fidelity and completeness
are approximately normally distributed but analyzed with the same
non-parametric suite for consistency. All pairwise comparisons apply
Bonferroni correction.

**Table 1.** *Descriptive Statistics for All Dependent Variables by Condition*

| Condition | *n* | Hallucination *M* (*SD*) | Evol. Fidelity *M* (*SD*) | Completeness *M* (*SD*) | Factual Retention *M* (*SD*) |
|---|---|---|---|---|---|
| Linear | 385 | 15.1 (30.9) | 95.6 (2.8) | 97.6 (1.7) | 95.6 (4.4) |
| Ring | 385 | 12.1 (27.8) | 96.3 (2.1) | 97.6 (1.5) | 95.8 (3.7) |
| Hub — Standard | 385 | 10.3 (26.7) | 96.6 (1.1) | 98.0 (1.0) | 95.8 (3.3) |
| Hub — High Capability | 385 | 6.2 (15.0) | 96.2 (2.2) | 97.8 (1.9) | 96.8 (3.7) |
| Hierarchy — Standard | 385 | 5.2 (17.2) | 96.9 (0.8) | 98.3 (0.9) | 96.1 (3.2) |
| Hierarchy — High Capability | 385 | 2.6 (10.3) | 97.0 (1.5) | 98.6 (1.2) | 97.2 (2.7) |
| Lattice — Standard | 560 | 11.7 (26.8) | 96.0 (2.9) | 97.3 (2.8) | 95.8 (3.6) |
| Lattice — Implicit | 560 | 7.2 (19.9) | 96.3 (2.7) | 97.8 (2.2) | 96.2 (4.0) |
| Lattice — Declared | 560 | 8.3 (21.2) | 96.0 (3.2) | 97.7 (2.5) | 96.4 (4.1) |
| Bilattice — Standard | 630 | 15.7 (30.8) | 94.9 (4.6) | 96.4 (4.5) | 95.4 (3.8) |
| Bilattice — Implicit | 630 | 12.5 (26.6) | 95.3 (3.8) | 97.1 (3.4) | 96.0 (4.2) |
| Bilattice — Declared | 630 | 11.7 (26.2) | 94.9 (4.9) | 96.7 (4.1) | 95.0 (5.6) |

*Note.* All dependent variables are scored 0–100. Hallucination is zero-inflated and right-skewed (27% zeros across all conditions); means are reported for comparability across DVs. *n* reflects all nodes across all hops, seeds, and lineages within each condition. Lattice and bilattice conditions have higher *n* due to greater node count per chain in those topologies.

Figure 1 summarizes the per-topology mutation profile across the three primary mutation types. The figure makes the multidimensional pattern visible: directed hierarchy minimizes all three mutation types; bidirectional lattice maximizes drift and fabrication while also producing the highest cross-lineage divergence; hub-and-spoke achieves near-zero divergence but elevated fabrication; linear chain shows substantial fabrication driven by long single-input chains; lattice occupies an intermediate position. Topology effects are not collapsible to a single quality dimension, and a topology that is best on one mutation type is not necessarily best on the others.

![Figure 1. Per-topology error profile across drift, divergence, and fabrication. Drift is operationalized as 100 minus mean evolutionary fidelity (all hops); divergence is the cell-level cross-lineage standard deviation of evolutionary fidelity at the terminal hop, computed per (topology × capability × seed) cell; fabrication is mean hallucination across all hops. Hierarchy XL-SD is shown as n/a because the canonical XL-SD computation uses chain_id = main at hop 11, which does not apply directly to the directed hierarchy structure.](figures/Figure_1.png)

**Figure 1.** Per-topology error profile across drift, divergence, and fabrication. Drift is operationalized as 100 minus mean evolutionary fidelity (all hops); divergence is the cell-level cross-lineage standard deviation of evolutionary fidelity at the terminal hop, computed per (topology × capability × seed) cell; fabrication is mean hallucination across all hops. Hierarchy XL-SD is shown as n/a because the canonical XL-SD computation uses chain_id = main at hop 11, which does not apply directly to the directed hierarchy structure.

**H1: Network Topology and Fabrication**

H1 predicted that topology would predict fabrication through two
mechanisms—synthesis fabrication at multi-input nodes and sequential
reconstruction fabrication at single-input nodes—with hierarchical
structures lowest, bidirectional lattice high, and linear chains high
when content is narratively complex. This hypothesis is partially
supported. Topology significantly predicted fabrication, and
hierarchical structures showed the lowest fabrication rates, consistent
with the proposed protective role of constrained routing. However,
fabrication was not confined to synthesis structures: linear chains
produced high absolute fabrication for narratively complex content,
indicating that repeated single-input reconstruction can generate
fabrication even without input reconciliation. The pattern requires the
two-mechanism account proposed under H1.

A Kruskal-Wallis test on hallucination by topology was significant,
H(5) = 285.1, p < .001, η² = .048. Pairwise post-hoc comparisons
(Bonferroni-corrected) revealed the following ordering. Directed
hierarchy produced the lowest hallucination (M = 3.9, Mdn = 2.0),
followed by hub-and-spoke (M = 8.3, Mdn = 3.0), lattice (M = 9.0, Mdn =
3.0), ring (M = 12.1, Mdn = 3.0), bidirectional lattice (M = 13.3, Mdn =
3.0), and linear (M = 15.1, Mdn = 3.0). Hierarchy was significantly
lower than all other topologies (all p_bonf < .001). Linear chain
produced significantly more hallucination than hierarchy (p_bonf < .001),
hub (p_bonf = .003), and lattice (p_bonf = .002), but did not
significantly differ from ring or bidirectional lattice after correction.
The bidirectional lattice was significantly higher than hierarchy, hub,
lattice, and ring (all p_bonf < .001), but did not significantly exceed
linear chain (p_bonf = .12).

The two mechanisms appear to operate in different topologies.
Bidirectional lattice hallucination was significantly higher than hub
(r_rb = .17, p < .001), hierarchy (r_rb = .39, p < .001), and ring
(r_rb = .11, p < .001), consistent with synthesis fabrication elevated
by iterative back-communication. Lattice was significantly lower than
linear chain (p_bonf = .002, r_rb = .10), and bidirectional lattice did
not significantly exceed linear chain (p_bonf = .12). Linear chain\'s
high absolute fabrication rate, driven substantially by narratively
complex content (see H5), is consistent with sequential reconstruction
fabrication: long single-input chains process ambiguous material
through repeated paraphrase under model priors, accumulating untraceable
content even without any synthesis decision. Synthesis fabrication and
sequential reconstruction fabrication thus appear as distinct
contributors that the topology comparison alone cannot fully separate;
H5 below provides additional evidence that complex content amplifies the
linear-chain effect specifically.

Final-hop analysis (terminal node only) strengthened all effects. At
hop 11, topology explained η² = .102 of hallucination variance,
approximately double the all-hops estimate, confirming that topology
effects compound across the chain. Hierarchy high-capability remained
the lowest (M = 6.0 at final hop); linear chain was worst among
sequential structures (M = 18.3); bidirectional lattice was worst
overall under declared capability (M = 28.3).

**H2: Network Structure and Cross-Lineage Divergence**

H2 predicted that centralized structures would produce lower
cross-lineage divergence (XL-SD) than distributed synthesis structures.
This hypothesis is strongly supported.

A Kruskal-Wallis test on XL-SD by topology was significant, H(4) =
25.67, p < .001, η² = .333, a large effect. Hub-and-spoke produced
near-zero divergence (M = 0.10, Mdn = 0.00): all five lineages arrived
at essentially identical final outputs across all seven seeds. Bilattice
produced the highest divergence by a substantial margin (M = 3.89, Mdn
= 4.03). Lattice (M = 1.39), linear (M = 1.63), and ring (M = 1.43)
occupied an intermediate position, not significantly different from
each other after correction.

OLS regression predicting XL-SD from topology and capability condition
(R² = .329, F(7,62) = 4.35, p < .001) confirmed that topology was the
dominant predictor. Hub was 3.65 points lower than bilattice (the
reference category; p = .001); lattice was 2.50 points lower (p < .001).
Capability condition did not significantly predict XL-SD in any
comparison (all p > .39), providing initial support for H7.

**H3: Capability Placement and Asymmetry, and Fabrication**

H3 predicted that higher-capability models at structurally
consequential positions would reduce fabrication relative to
standard-capability configurations, with the strongest effects under
capability placement (hub, hierarchy) and smaller effects under
capability asymmetry (lattice, bilattice). H3 is supported. Higher-
capability models placed at structurally amplified positions reduced
hallucination substantially in hub-and-spoke and directed hierarchy
networks; capability asymmetry between parallel chains in lattice and
bilattice produced smaller and topology-specific effects, as predicted.
These results are consistent with the interpretation that upgraded
nodes generate more stable downstream inputs; they do not, by
themselves, demonstrate status-like deference.

*Hub-and-spoke.* A higher-capability hub (Claude Sonnet 4.6) reduced
hallucination by 39.9% relative to the standard-capability hub
(M = 6.2 vs. 10.3; Mann-Whitney U = 63,437, p < .001, r_rb = .14).
Capability placement also improved factual retention (r_rb = .23,
p < .001). The effect on evolutionary fidelity was small and in the
unexpected direction (standard slightly higher; r_rb = .08), suggesting
that the placement benefit is specific to fabrication suppression
rather than general fidelity improvement.

*Directed hierarchy.* A higher-capability upper tier produced the
clearest capability-placement effect in the dataset: 49.7% reduction in
hallucination (M = 2.6 vs. 5.2; U = 88,076, p < .001, r_rb = .19),
improved factual retention (r_rb = .20, p < .001), and improved
completeness (r_rb = .22, p < .001). The hierarchy high-capability
condition was the cleanest condition in the entire dataset across all
DVs.

*Lattice.* Capability conditions did not significantly reduce
hallucination in the lattice (KW H(2) = 5.04, p = .080, η² = .002).
Factual retention and completeness showed small but significant
improvements under both implicit and declared conditions relative to
standard (r_rb ≈ .10--.18). The absence of a hallucination effect in
the lattice distinguishes it from hub and hierarchy and is consistent
with the prediction that capability asymmetry between parallel chains
(asymmetry feeding a single synthesis decision) produces weaker
fabrication effects than capability placement at a structurally
amplified node. The hallucination reduction observed under
bidirectional lattice declared (below) suggests that asymmetry effects
emerge most clearly where iterative back-communication amplifies them.

*Bidirectional lattice.* The declared condition reduced hallucination
significantly relative to standard (M = 11.7 vs. 15.7; r_rb = .11,
p = .003). The implicit condition showed a 20% reduction that did not
reach corrected significance (M = 12.5 vs. 15.7; p_bonf = .36).

**H4: Capability Disclosure**

H4 predicted that capability disclosure would not improve information
quality beyond capability asymmetry: if synthesis nodes respond
primarily to the semantic properties of their inputs rather than to
explicit source labels, declared and implicit conditions should produce
statistically indistinguishable outcomes. H4 is supported as a null
disclosure effect. Declared capability labels did not reliably improve
information quality relative to implicit capability asymmetry. This
pattern provides no evidence for status-like deference to explicit
source labels. Instead, synthesis nodes appear to respond primarily to
the semantic properties of the inputs they receive.

For lattice, pairwise comparisons between the implicit and declared
conditions showed no significant differences on any DV (all p_bonf >
.017). For bidirectional lattice, implicit and declared did not
significantly differ on hallucination (p_bonf = ns), factual retention
(p_bonf = .019, marginal), or completeness (p_bonf = ns). The one
partial exception was bilattice factual retention, where implicit
outperformed declared (r_rb = .09, p_bonf = .019), a result that runs
counter to the signaling hypothesis.

The consistent pattern across conditions is that whether a synthesis
node is told which input came from a higher-capability system does not
meaningfully alter its output quality beyond what the quality of those
inputs alone produces. Under the conditions tested, capability
disclosure does not add detectable effects beyond capability asymmetry.

**H5: Content Complexity as a Moderator (Exploratory Bartlett Comparison)**

H5 predicted that topology effects on hallucination would be larger for
the Bartlett stimulus than for organizational content. This hypothesis
is supported within the bounds noted below.

Kruskal-Wallis on hallucination within seed type confirmed the
interaction: topology η² = .055 for organizational seeds, η² = .121
for the Bartlett seed. Topology effects more than doubled for
narratively complex content. The Bartlett seed generated 9.6× more
hallucination than organizational seeds overall (M = 44.1 vs. 4.6;
Mann-Whitney r_rb = .726, p < .001), with seed identity explaining
30.1% of hallucination rank variance across all conditions (KW
H(6) = 1,773.25, p < .001, η² = .301).

The topology × content type interaction was not uniform. Hub showed the
most dramatic amplification: Bartlett hallucination was 19.5× the
organizational mean (M = 44.3 vs. 2.3). Hierarchy showed the smallest
amplification (11.0×; M = 17.5 vs. 1.6), consistent with its structural
buffering of fabrication. Linear chain produced the worst absolute
Bartlett performance (M = 64.2, Mdn = 100). The modal output of a
linear chain with the Bartlett seed was maximum hallucination,
consistent with the sequential-reconstruction-fabrication mechanism
proposed under H1: long single-input chains processing
schema-inconsistent material accumulate untraceable content as model
priors fill gaps and regularize anomalies.

The inference here must remain narrow. One Bartlett-style stimulus
cannot support a general claim about narratively complex content. The
present design does not separate narrative complexity from the
idiosyncratic features of this specific stimulus; the result is
consistent with the possibility that schema-inconsistent narrative
content amplifies topology-dependent mutation, but a stronger inference
would require a stimulus set that varies narrative complexity, schema
consistency, and ambiguity orthogonally. We treat the Bartlett
comparison as an exploratory demonstration that points to a
generalizable pattern, not as a definitive test.

**H6: Compounding Effects Across Hops**

H6 predicted that topology effects would be larger at terminal nodes
than at early positions. This hypothesis is supported across all
dependent variables.

Comparing all-hops η² to final-hop η² by DV: evolutionary fidelity
increased from .042 to .085 (+.043); hallucination from .048 to .102
(+.054); completeness from .053 to .095 (+.042). Factual retention
showed no meaningful change (.005 to .006), consistent with its
insensitivity to topology reported under H7 below. The approximate
doubling of effect sizes from intermediate to terminal nodes confirms
that topology differences compound across the chain and that studies
measuring only intermediate outputs underestimate practical topology
effects by approximately half.

Hop trajectory analysis confirmed non-linear accumulation for some
topologies. Linear chain showed monotonic degradation with widening
variance across hops, the expected telephone game pattern. Hierarchy
was strikingly flat across the upper and middle tiers (evol_fidelity M
≈ 97.1 at hops 1--8), degrading only at lower-tier terminal nodes
(M = 96.3 at hops 9--11). Bilattice entered the synthesis merge point
already at lower fidelity (M = 93.7 at hop 6) before further degradation.

**H7: Capability Configuration Does Not Reduce Cross-Lineage Divergence**

H7 predicted that capability condition would not reduce cross-lineage
divergence once topology was controlled, because divergence is expected
to be an architectural property of branching and synthesis structure
rather than a local capability property of individual nodes. H7 is
supported. Capability condition does not reduce cross-lineage divergence
after topology is controlled. This indicates that divergence is produced
by branching and synthesis architecture rather than by local model
capability. Upgrading models may reduce fabrication, but it does not
solve lineage-level inconsistency.

In the OLS regression reported under H2 (R² = .329), capability
coefficients were uniformly non-significant: high capability
(β = −0.49, p = .731), implicit (β = −0.66, p = .418), standard
(β = −0.69, p = .397). Within-bilattice Kruskal-Wallis on XL-SD by
capability condition was also non-significant (H(2) = 1.93, p = .38,
η² = −.004). The architectural property cannot be remediated by
upgrading model capability at any node position.

**Factual Retention as a Distinct Phenomenon**

A finding worth foregrounding rather than relegating to a footnote:
factual retention behaves very differently from the other dependent
variables. It shows near-zero differentiation by topology across all
conditions (η² = .005 across all hops; η² = .006 at the final hop) and
is only weakly correlated with hallucination (r = −.051). A node can
fabricate substantial novel content while retaining most or all of the
factual anchors present in its input.

This dissociation matters. Hallucination, as measured here, is the
addition of specific details, claims, or facts not present in the
seed—including causal claims, temporal restructurings, and
*epistemic-status fabrications* in which a projection becomes a stated
outcome or a conditional becomes a declarative. Factual retention is
the survival of seed-side anchors. The two measures move almost
independently, which means that a transmission can retain every named
entity, every number, and every date in the seed while
introducing fabricated relations among them. The spoilage example
above is a paradigm case: numbers, percentages, and entities are
preserved while "would increase... at a projected cost" becomes "have
resulted in... costing."

The implication for evaluation practice is direct. Researchers and
practitioners evaluating M2M pipeline quality using fact-check-style
metrics or named-entity recall are measuring a dimension that is
insensitive to the structural effects documented here. Fact-retention
audits will systematically miss epistemic-status fabrication and
synthesis-driven causal addition, both of which are the dominant failure
modes in the conditions where mutation matters most. Hallucination
(addition) and cross-lineage divergence (architectural variance) are
the appropriate primary measures for topology-comparative work; factual
retention is best understood as a distinct phenomenon answering a
different question.

**Summary**

Table 2 summarizes support for each hypothesis. H2, H6, and H7 are
supported; H3 is supported as a capability-placement effect; H4 is
supported as a null disclosure effect; H5 is supported within the
bounds of a single Bartlett stimulus; H1 is partially supported, with
the omnibus topology effect on fabrication confirmed but the original
ordering claim requiring the two-mechanism account developed under H1.
The overall pattern establishes that network topology is the primary
determinant of all three mutation types. Capability placement reduces
fabrication where the upgraded node\'s outputs are structurally
amplified (hub, hierarchy); capability asymmetry between parallel
chains produces smaller and topology-specific effects (lattice,
bilattice); capability disclosure does not reliably add detectable
effects beyond asymmetry; and capability configuration does not reduce
architectural divergence at all. Factual retention behaves as a
distinct phenomenon largely insensitive to topology and only weakly
correlated with hallucination.

**Table 2.** *Summary of Hypothesis Tests*

| Hypothesis | Prediction | Key Result | Verdict |
|---|---|---|---|
| H1 | Topology predicts fabrication through synthesis fabrication and sequential reconstruction fabrication; hierarchy lowest, bilattice high, linear chains high for narratively complex content | KW H(5) = 285.1, p < .001, η² = .048; hierarchy lowest (*M* = 3.9); linear chain highest overall (*M* = 15.1); bidirectional lattice highest among synthesis structures (*M* = 13.3); linear and bilattice not significantly different (*p*_bonf = .12) | Partially supported (omnibus effect supported; two-mechanism account required) |
| H2 | Centralized structures produce lower cross-lineage divergence than synthesis structures | KW H(4) = 25.67, p < .001, η² = .333; hub-and-spoke near-zero (*M* = 0.10); bilattice highest (*M* = 3.89) | Supported |
| H3 (capability placement and asymmetry) | Higher-capability models at structurally consequential positions reduce fabrication; strongest under capability placement (hub, hierarchy), smaller under capability asymmetry (lattice, bilattice) | Hub: 39.9% reduction (*r*_rb = .14, p < .001); hierarchy: 49.7% reduction (*r*_rb = .19, p < .001); lattice: no significant hallucination effect; bilattice declared: significant 25% reduction | Supported (placement effects substantially larger than asymmetry effects, as predicted; consistent with "upgraded nodes generate more stable downstream inputs"; not a demonstration of status-like deference) |
| H4 (capability disclosure) | Capability disclosure does not improve quality beyond capability asymmetry | No significant differences between implicit and declared conditions on any DV across lattice or bilattice (all *p*_bonf > .017); one marginal exception runs counter to signaling | Supported (null disclosure effect; no evidence for status-like deference to explicit labels) |
| H5 | Topology effects on hallucination are larger for the Bartlett stimulus than for organizational content | Topology η² = .055 (organizational seeds) vs. .121 (Bartlett seed); Bartlett generates 9.6× more hallucination overall (*r*_rb = .726, p < .001) | Supported within the bounds of a single Bartlett stimulus (exploratory) |
| H6 | Topology effects are larger at terminal nodes than at intermediate positions | All-hops vs. final-hop η²: evol. fidelity .042 → .085; hallucination .048 → .102; completeness .053 → .095 | Supported |
| H7 | Capability condition does not reduce cross-lineage divergence once topology is controlled | All capability coefficients non-significant in OLS (all *p* > .39); within-bilattice KW on XL-SD by capability condition *p* = .38, η² ≈ .000 | Supported (architectural property, not local capability) |

**Discussion**

This study set out to examine how network topology and capability configuration shape information mutation in M2M communication systems. Across 5,880 node-level transmission events drawn from 420 chains spanning six topologies and three capability conditions, the results establish a consistent picture: network structure is the primary determinant of all three mutation types; capability placement at structurally consequential positions reduces fabrication where downstream amplification is high; capability asymmetry between parallel chains produces smaller and topology-specific effects; capability disclosure does not add detectable effects beyond asymmetry; and factual retention behaves as a distinct phenomenon largely insensitive to topology. We discuss the theoretical implications in turn, then address what these dependent variables do and do not measure, audit implications, and limitations.

**Topology as the primary lever**

The most consequential finding of this study is also the most general: topology explains more variance in information mutation than any other factor. Effect sizes for topology on hallucination (η² = .048, final-hop η² = .102), evolutionary fidelity, completeness, and especially cross-lineage divergence (η² = .333) are large relative to the capability-condition effects measured here and large relative to what the human network literature typically reports for structural predictors of diffusion outcomes. Architectural decisions appear to carry more leverage for information quality in M2M systems than capability investments at non-amplified positions. Moving from a linear chain to a directed hierarchy reduces fabrication by approximately half; no capability condition achieves a comparable reduction at non-amplified positions.

The topology effects observed here are not merely quantitative but qualitative. Different topologies produce different *kinds* of mutation, and these mutations have different relationships to impairment. Linear chains produce *drift*: cumulative semantic movement along the lineage, including some benign paraphrase as well as cumulative reconstruction fabrication that accumulates in long single-input chains processing ambiguous content. Hub-and-spoke and hierarchical structures produce low drift but non-zero fabrication concentrated at high-traffic integration nodes. Synthesis structures (lattice and bidirectional lattice) produce *divergence*: between-lineage dispersion among independent transmissions from the same seed, with parallel lineages arriving at qualitatively distinct information states that cannot be attributed to any single transmission event. These are not points on a single quality continuum; they are mechanistically distinct failure modes, carrying different diagnostic signatures and different remediation logics.

The hub-and-spoke topology illustrates the multidimensional structure of these mutation types most starkly. Hub-and-spoke produces near-zero cross-lineage divergence (M = 0.10) because lineages are forced through a common processing bottleneck: every message passes through the same hub, so independent runs cannot drift apart. The same bottleneck, however, concentrates whatever semantic tendencies, biases, or fabrication risks the hub model carries—if the hub fabricates, every lineage inherits the same fabrication. Hub-and-spoke is thus best understood as a single bottleneck-tradeoff mechanism: it reduces between-run variance at the cost of concentrating any model-specific drift or addition into a uniformly propagated form. Lower variance in hub deployments is not the same as lower error; it is *systematic* rather than *idiosyncratic* mutation. This framing applies, in attenuated form, to directed hierarchy as well, where upper-tier outputs constrain a cascading set of downstream computations.

This three-type framework, together with the two-mechanism account of fabrication developed under H1, is the primary theoretical contribution of the present study. Drift, divergence, and fabrication have different antecedents (hop depth, structural branching, synthesis demand), different distributions (monotonic, bimodal, zero-inflated skewed), and different practical consequences for organizations. A pipeline with high drift is partly recoverable by shortening the chain or by adding terminal source comparisons. A pipeline with high divergence cannot be remediated by shortening or by upgrading nodes; it requires architectural restructuring or explicit reconciliation protocols. A pipeline with high fabrication requires different remediations depending on whether the source is synthesis (provenance-aware auditing at multi-input nodes) or sequential reconstruction (terminal source comparison and chain-length limits for complex content). Treating these as a single "error" dimension, as much prior work implicitly does, obscures the diagnostic information needed to intervene.

**Capability Placement, Not Status Signaling**

The findings do not support a human-status analog in which source labels produce deference independent of contribution quality. They support a capability-placement mechanism. Stronger models reduce fabrication when their outputs occupy structurally consequential positions, but explicit labels indicating higher capability do not meaningfully improve quality. This distinguishes M2M systems from human SCT dynamics. In human groups, status cues can influence adoption even when decoupled from substantive quality. In these M2M networks, the label itself appears weak or inert under the tested conditions.

In SCT terms, the M2M agents in this study appear sensitive to capability as embodied in generated outputs or structurally consequential processing, but not to capability as an explicit status cue. The one partial exception in the data, where the implicit condition marginally outperformed the declared condition in bilattice factual retention, runs counter to the signaling hypothesis—if anything, the explicit label introduces a slight integration cost rather than a deference benefit. Under the conditions tested, declared capability is not behaving as a status characteristic.

The reading for organizational practice is correspondingly narrow. Capability placement at hubs, hierarchy apices, and other structurally amplified positions reduces fabrication; the pattern is consistent with the interpretation that upgraded nodes generate more stable downstream inputs, which then propagate to many downstream positions. We did not directly test the mediator (input-quality-mediated downstream stability), and the design therefore supports a behavioral conclusion (lower fabrication when capability is placed at amplified nodes) more strongly than a mechanistic one. Capability disclosure—telling a downstream node that an input came from a higher-capability source—does not, on the present evidence, additionally move outcomes. We do not interpret this as a demonstration that machine status is impossible in principle. We interpret it as evidence that, with these models and these labels, source-cue weighting independent of input quality is not detectable.

**Information Mutation Versus Task Performance**

A note on the normative stance of these dependent variables. Hallucination, divergence, fidelity, and completeness measure transmission, not task performance. A topology can preserve information poorly but still produce a useful summary, and a synthesis node may infer a useful abstraction or improve readability. From a task-performance standpoint, that may be desirable. From an information-mutation standpoint, it is still a mutation if unsupported by the input. We do not take the position that all mutations are bad, nor that fidelity is the only thing organizations should optimize for. We take the position that fluent abstraction and faithful transmission are different desiderata, that they can move independently, and that organizations choosing to deploy M2M pipelines need to know which one they are getting and where.

**Content Complexity as a Moderator (Bartlett Comparison)**

The H5 results suggest that topology effects are not uniform across content types. The single Bartlett-style stimulus produced 9.6× more hallucination than organizational content overall, and topology effects on hallucination more than doubled (η² from .055 to .121) for that seed. The linear chain produced maximum hallucination (Mdn = 100) for the Bartlett seed, meaning the modal terminal output of a simple sequential pipeline processing this stimulus was complete fabrication relative to the original.

The connection to Bartlett (1932) is suggestive but should be drawn carefully. We use *schema* analogically rather than literally. In humans, schemas are cognitive structures that guide encoding, storage, and recall. In LLMs, the analogous force is the model\'s learned distribution over plausible continuations and coherent narrative forms—distributional regularities, alignment preferences, decoding tendencies, and instruction-following priors. Both can regularize anomalous input, but the underlying mechanisms differ, and conflating them risks misattributing cognitive properties to LLMs. What our data show is that schema-inconsistent narrative material moves further under M2M transmission than organizational content does, and that the topology effect is amplified for that material. What our data do not show is that LLM schemas operate the way human schemas do.

The inference must also remain narrow on the stimulus side. One Bartlett-style stimulus cannot support a general claim about narratively complex content. The result is consistent with the possibility that schema-inconsistent narrative content amplifies topology-dependent mutation, but the present design does not separate narrative complexity from the idiosyncratic features of this specific stimulus. We treat the Bartlett comparison as an exploratory demonstration that points toward a generalizable pattern, and we flag the cross-stimulus generalization as a priority for future work.

**Human-Machine Parallels**

A central motivation for this study was to examine the degree to which human network diffusion findings generalize to M2M systems. The results suggest a pattern of partial generalization with theoretically interpretable departures.

The pattern of compounding effects (H6) is continuous with human network findings. Brashears and Gladstone (2016) documented rapid semantic degradation across transmission events; we find the same monotonic degradation in linear chains and the same compounding logic. Topology effects at terminal nodes are approximately double those at intermediate nodes. The telephone game metaphor applies to sequential M2M structures as fully as it applies to human ones.

The nature of the errors, however, diverges. In human networks, semantic error takes the form of simplification, schematization, and assimilation to familiar narratives—processes driven by working memory constraints and meaning-seeking tendencies. In M2M networks, the dominant error at synthesis nodes is fabrication: confident generation of content not present in or traceable to the inputs. This is a qualitatively different failure mode, arguably more dangerous in organizational contexts because it is fluent, plausible, and unsignaled. A human relay that misremembers a figure may produce an obviously wrong or obviously garbled output; an LLM that fabricates replaces the input with a semantically coherent alternative that may be indistinguishable from accurate transmission. The "broken telephone" analogy understates the risk.

Brashears and Gladstone (2016) identified a diversification mechanism in human networks: error correction efforts, paradoxically, increased the number of distinct mutant forms in circulation, producing innovation alongside inaccuracy. A related but mechanistically distinct process operates in M2M synthesis structures. When parallel lineages are merged, divergence is not corrected but concentrated: the synthesis node\'s output reflects one particular resolution of the divergent inputs, which may amplify some lineages\' drift while suppressing others\'. The result is not diversification through error correction but selective consolidation through synthesis, a process that could entrench specific mutations as the authoritative version while discarding others. Whether this has the same innovation-enabling upside as the human diversification effect is an open question and a priority for future work.

**Audit Implications**

The findings translate into conditional audit principles rather than universal architectural prescriptions. Different topologies and content types create different epistemic risks; the appropriate audit response depends on which risks dominate.

*Linear chains require terminal comparison against source material*, especially for narrative or ambiguous content. The dominant failure mode in linear chains is sequential reconstruction fabrication, which is invisible at any single hop and emerges only as cumulative drift from origin. Audits limited to step-by-step coherence will miss it.

*Synthesis structures require provenance-aware auditing.* Fluent reconciliation can fabricate relations not present in any input; the synthesis node may produce a coherent declarative not entailed by either source. Auditing the synthesis output against each individual input, not just against an aggregate, is the appropriate stance.

*Hierarchies may reduce fabrication but should be audited for compression and upstream semantic lock-in.* The buffering benefit of constrained tier-by-tier processing comes at a cost: lower-tier nodes process under upper-tier constraints, and biases introduced upstream cannot be readily corrected downstream. Audits should attend to omission and to whether terminal outputs reflect upstream framing more than seed content.

*Hub structures reduce variance but concentrate model-specific semantic bias.* The same hub that delivers near-zero divergence is also the structural location where one model\'s tendencies propagate uniformly to the network. Audits should sample across hub deployments and watch for systematic, rather than random, drift.

*Fact-retention audits are insufficient.* The dissociation between hallucination and factual retention documented in this study is direct evidence that pipelines can preserve numbers, names, and entities while altering modality, causality, or evidentiary status. Evaluations limited to fact-check or named-entity metrics will produce false reassurance.

Table 3 summarizes the per-topology mapping between architecture, dominant mutation risk, mechanism, and recommended audit remedy.

**Table 3.** *Topology-Specific Mutation Risks and Audit Remedies*

| Topology | Dominant mutation risk | Mechanism | Audit remedy |
|---|---|---|---|
| Linear chain | Drift; sequential reconstruction fabrication for complex content | Cumulative reconstruction across single-input hops | Shorten chain where possible; terminal comparison against source material, especially for narrative or ambiguous content |
| Hub-and-spoke | Concentrated fabrication; uniform propagation of hub-specific tendencies | Bottleneck amplification of a single integration node | Audit hub outputs directly; source-grounded checks at the hub; sample across hub deployments to detect systematic rather than idiosyncratic mutation |
| Directed hierarchy | Low fabrication but possible compression and upstream lock-in | Constrained cascade with upper-tier framing constraining lower tiers | Audit for omission and for whether terminal outputs reflect upstream framing more than seed content; spot-check upper-tier inputs against final-tier outputs |
| Lattice | Cross-lineage divergence | Parallel lineage development without iterative reconciliation | Reconciliation protocol at synthesis; audit synthesis output against each individual input, not against an aggregate |
| Bidirectional lattice | Divergence plus synthesis fabrication | Iterative reconciliation across parallel chains; back-communication amplifies both convergence and synthesis confabulation | Provenance-aware synthesis audit; constrain back-communication rounds; audit terminal synthesis output against original seeds |
| Ring with shortcuts | Heterogeneous fidelity across terminal nodes | Variable path length to the terminus | Path-aware terminal audit; flag terminal nodes by hop distance from origin |

*Note.* Across all topologies, fact-retention audits alone are insufficient: factual anchors (numbers, names, entities) can survive intact while modality, causality, temporal structure, or evidentiary status mutates. Hallucination and cross-lineage divergence are the appropriate primary measures for topology-comparative audit work.

These principles do not collapse to a recommendation that organizations adopt one architecture. Different deployments face different content profiles and different risk tolerances; the appropriate audit posture depends on which mutation type dominates the use case. The contribution of the present study is to map the topology-to-mutation-type correspondences so that deployments can target their audits accordingly.

**Limitations**

Several limitations bound the generalizability of these findings.

*Sampling, representation, and generalizability.* The study examines six theoretically selected M2M topologies rather than a probability sample of organizational AI deployments. The six structures are intended to be representative of the major architectural classes in current and emerging M2M practice—sequential single-input routing (linear chain), centralization with bottleneck integration (hub-and-spoke), tier-ordered cascade (directed hierarchy), parallel synthesis without back-communication (lattice), iterative parallel synthesis with back-communication (bidirectional lattice), and distributed routing with path-length heterogeneity (ring with shortcuts)—rather than to estimate the prevalence of any one of these in the population of real systems. The findings should generalize to the extent that real M2M systems share the modeled structural features that drive the documented effects: path length, centralization, input multiplicity, synthesis demand, feedback, and capability configuration at structurally consequential nodes. Generalization beyond those features is bounded by the synthetic LLM pipeline (one model family, one stimulus language, a small set of seed messages, fixed chain lengths). The study's strongest claims are accordingly topology-comparative and mechanism-oriented—how does mutation differ by architectural class, and through what processes—rather than population-prevalence claims about how often a given topology appears in deployed systems.

*Model-family dependence.* Both transmission and coding in this study rely on the Claude model family (Haiku 4.5 and Sonnet 4.6). The findings are therefore about topology and capability configuration *under this model ecology*. Whether the topology effects observed here generalize across model families—GPT, Gemini, Llama, and others—and whether the null disclosure finding holds when models are drawn from different providers, remains an open question. Replication across model families is a priority for subsequent work, and our infrastructure is well positioned to support it.

*Operationalization of machine authority.* The present study operationalizes authority-like mechanisms through model capability tier and explicit capability labels. It does not test other plausible bases of authority, including institutional provenance, domain specialization, reliability histories, confidence scores, or externally validated accuracy metrics. Nor does it fully separate source quality from source identity in the implicit condition, because higher-capability models may produce text that differs in both substance and style. The findings therefore support a narrow conclusion: explicit capability labels did not affect synthesis outcomes beyond the properties of the generated inputs under the tested conditions. They do not rule out richer status-like effects under richer manipulations.

*Topology coverage.* The six topologies examined here, while representative, do not exhaust the space of M2M architectures. Dynamic networks, networks with feedback loops beyond the bidirectional lattice, larger hub-and-spoke configurations with multiple tiers of fan-out, and hybrid human-machine networks with humans at specific structural positions all warrant study and are outside the present empirical scope.

*LLM coding and within-instrument inference.* All semantic coding is performed by an LLM coder (Claude Sonnet 4.6). Our claims about absolute fidelity values are correspondingly limited; we restrict inference to within-instrument comparisons across topology and capability conditions. Within-instrument comparison neutralizes coder biases that are constant across conditions, but a coder bias that interacts with topology, content type, or text style could in principle inflate or deflate condition contrasts. We have not validated against an external coder, a non-LLM embedding metric, or a human comparison sample; the LLM-coder boundary is acknowledged and inferences are framed accordingly.

*Statistical inference at the node level.* Node-level Kruskal-Wallis tests treat within-chain observations as independent and therefore overstate effective n. We rely primarily on effect sizes, on chain- and cell-level summaries, and on the consistency of effects across analysis levels (all-hops, final-hop, cell-level XL-SD). Appendix A reports mixed-effects robustness analyses with random intercepts for chain (run); the substantive pattern is unchanged—topology effects survive, capability-configuration effects on hallucination severity survive at the node level (driven primarily by placement rather than disclosure), capability disclosure remains null, and capability does not predict cross-lineage divergence after topology is controlled.

*Single Bartlett stimulus.* The exploratory Bartlett comparison rests on a single schema-inconsistent narrative seed. The pattern is suggestive but the design does not separate narrative complexity from the idiosyncratic features of this stimulus. Generalizing to "narratively complex content" as a category would require a stimulus set that varies narrative complexity, schema consistency, and ambiguity orthogonally.

**Future Work**

A stronger test of status-signaling effects in M2M networks would require varying source labels independently of actual capability. Possible designs include: a higher-capability model labeled as standard, a standard model labeled as higher-capability, equal-quality inputs randomly labeled high versus low capability, institutional provenance labels (e.g., enterprise vs. open-source), domain-specialist labels, reliability-history labels, and confidence labels detached from correctness. These designs would test status signaling more directly than the present study can. They would also help separate the four constructs developed here—capability placement, capability asymmetry, capability disclosure, and authority-like adoption—at finer resolution than the implicit-versus-declared contrast permits.

Brashears and Gladstone (2016) closed their study with an explicit call for future work on complex network topologies, simulation approaches, and prestige/status effects. The present study addresses all three. The findings open their own agenda: the interaction of topology and content type in larger parameter sweeps; the conditions under which synthesis fabrication propagates versus attenuates across subsequent hops; the viability of architectural interventions (e.g., explicit grounding requirements at synthesis nodes) as countermeasures; cross-model-family replication of topology effects; and ultimately the implications for the sociology of knowledge in a world where much of what we collectively know has passed through networks of artificial processors before reaching human recipients.

**Appendix A. Mixed-Effects Robustness Analyses**

The primary analyses in the main text use non-parametric methods (Kruskal-Wallis with pairwise post-hoc; Mann-Whitney U), chosen for the bounded and skewed distributions of the dependent variables. As noted in the Limitations, node-level non-parametric tests treat within-chain observations as independent and therefore overstate effective n. To address this, we re-estimate the primary topology and capability-configuration effects using mixed-effects and clustered models that explicitly model the nested structure of the data. The goal is narrow: do the topology and capability-configuration effects survive when chain, seed, and repeated node observations are modeled explicitly? They do.

*Specification.* Each node-level outcome is modeled with random intercepts for chain (run, n = 420) and fixed effects for topology, hop, hop squared, capability configuration, and seed type. Topology × hop interactions are included where appropriate. Seed is represented through fixed seed-type indicators (organizational vs Bartlett) rather than a random effect because the study contains only seven designed stimuli and the random-effect distribution would be poorly estimated at that scale; this is a design choice, not an omission. The dichotomous any-hallucination outcome is modeled using generalized estimating equations (GEE) with a binomial-logit link and run as the cluster, providing population-averaged estimates with cluster-robust standard errors. The positive-only severity model uses log1p-transformed hallucination on the subset where hallucination > 0, with random intercepts for chain. Chain-level terminal-hop models (n = 420 chains) use OLS for continuous outcomes and logistic GLM for the binary any-hallucination outcome; these treat the chain as the unit, eliminating within-chain dependence by construction. The cell-level XL-SD model (n = 196 cells) uses OLS at the (topology × capability × seed) cell level. Reference categories: topology = bidirectional lattice, capability condition = standard, seed type = organizational.

*Convergence and specification choices.* We report random-intercept-only models as the headline robustness specification. Random slopes for hop within chain were attempted but produced unstable estimates in some specifications; we therefore drop them, consistent with treating these models as robustness checks for direction and magnitude hierarchy rather than precise parameter recovery. Bayesian or full hierarchical specifications would be more elegant but unnecessary for the inferential question we pose. Table A.1 summarizes the omnibus topology and capability tests across all nine model specifications.

**Table A.1.** *Mixed-Effects Robustness Summary*

| Outcome | Model | Topology effect retained? | Capability effect retained? | Notes |
|---|---|---|---|---|
| Evolutionary fidelity (all hops) | LMM, random intercepts for chain; topology × hop fixed | Yes — Wald χ² = 504.4, *df* = 10, *p* < .001 | No — Wald χ² = 2.51, *df* = 3, *p* = .47 | Topology × hop interactions all significant; hierarchy and hub show smallest negative deviation from bilattice baseline |
| Completeness (all hops) | LMM, random intercepts for chain; topology × hop fixed | Yes — Wald χ² = 404.3, *df* = 10, *p* < .001 | Yes (marginal) — Wald χ² = 8.31, *df* = 3, *p* = .04 | Implicit condition shows positive coefficient on completeness; hierarchy and hub strongest topology effects |
| Any hallucination (binary) | GEE logistic, clustered by chain | Yes — Wald χ² = 42.18, *p* < .001 | No — Wald χ² = 4.82, *p* = .19 | Hierarchy reduces probability of any hallucination most strongly (β = −1.83); Bartlett seed type massively elevates probability (β = +5.46) |
| Hallucination severity given hallu > 0 (n = 4,290) | LMM, random intercepts for chain; log1p outcome | Yes — Wald χ² = 70.49, *df* = 5, *p* < .001 | Marginal — Wald χ² = 6.78, *df* = 3, *p* = .08; high-capability coefficient β = −0.17, *p* = .04 | Hierarchy largest severity reduction (β = −0.73); high-capability placement reduces severity at the node level conditional on any hallucination |
| Terminal hallucination (n = 420 chains) | OLS at chain level | Yes — Wald = 5.60, *p* < .001 | No — *p* = .58 | Capability effects are not retained in the single terminal-observation model; topology remains robust |
| Terminal any-hallucination (n = 420 chains) | Logistic GLM at chain level | Yes — Wald = 48.24, *p* < .001 | No — *p* = .79 | Hub strongest reduction at chain-terminal level (β = −3.61) |
| Terminal evolutionary fidelity (n = 420) | OLS at chain level | Yes — Wald = 12.11, *p* < .001 | No — *p* = .96 | Hub and hierarchy retain highest terminal fidelity |
| Terminal completeness (n = 420) | OLS at chain level | Yes — Wald = 11.67, *p* < .001 | No — *p* = .29 | Hub and hierarchy retain highest terminal completeness |
| Cell-level XL-SD (n = 196 cells) | OLS at cell level | Yes — Wald = 5.33, *p* < .001 | No — Wald = 0.34, *p* = .80 | *R*² = .377, F = 4.61, *p* < .001; reproduces the manuscript-reported H2 / H7 OLS within rounding |

*Note.* Reference category for topology contrasts is bidirectional lattice; coefficients therefore indicate effect *relative to bilattice*. "Topology effect retained" indicates a significant omnibus joint test on the topology coefficient vector. "Capability effect retained" indicates a significant omnibus joint test on the capability-condition coefficient vector. Bonferroni correction is not applied to the omnibus tests; pairwise contrasts within outcomes use uncorrected Wald *p*-values for transparency.

*Substantive read.* All nine omnibus topology tests are highly significant; topology is the dominant predictor under the robustness specifications reported here. Capability omnibus tests are mixed: capability-configuration effects on hallucination severity survive at the node level (consistent with the manuscript's H3 finding), driven primarily by placement rather than disclosure, but do not survive collapse to chain-level terminal outcomes. This suggests that capability placement is more visible in node-level trajectories than in single terminal summaries—consistent with the manuscript's framing of placement effects as operating across the cumulative chain rather than at any single endpoint. Capability disclosure (the implicit-vs-declared contrast inside the authority coefficients) does not produce a clear effect in any model, consistent with H4. Cross-lineage divergence remains an architectural property: the cell-level OLS shows the same topology-driven pattern reported in the main text, with capability coefficients all far from significance, consistent with H7.

The robustness analyses thus confirm the manuscript's substantive conclusions: (a) topology is the primary determinant of all three mutation types under any reasonable inferential specification; (b) capability placement reduces hallucination at structurally amplified positions; (c) capability disclosure does not behave like SCT-style status signaling; and (d) cross-lineage divergence is architectural, not capability-driven. The non-parametric tests in the main text describe this pattern with intuitive transparency; the mixed-effects models confirm that the pattern is not an artifact of treating within-chain node observations as independent. The reproducibility script is included with the data deposit (see Data Availability Statement).

**Data Availability Statement**

The data, code, prompts, and analysis scripts supporting the findings of this study will be made available in [REPOSITORY] at [DOI OR URL] upon publication. The deposit will include the simulation source (an HTML implementation regenerating the dataset end-to-end from an Anthropic API key), the 5,880-row primary dataset, the analysis script reproducing every numerical claim in the manuscript, and the mixed-effects robustness script reproducing Appendix A.

**Declaration of Generative AI and AI-Assisted Technologies in the Manuscript Preparation Process**

During the preparation of this work, the authors used generative AI and AI-assisted tools to support drafting, revision, language refinement, code development, and manuscript organization. Large language models were also used as part of the research design, as described in the Methods section, where LLM agents served as transmission nodes and semantic coders. After using these tools, the authors reviewed, verified, edited, and approved the content and take full responsibility for the content of the article.

**References**

Alansari, A., & Luqman, H. (2025). Large language models hallucination:
A comprehensive survey.

*arXiv preprint arXiv:2510.06265*.

Ashery, A. F., Aiello, L. M., & Baronchelli, A. (2025). Emergent social
conventions and collective bias in LLM populations.

*Science Advances*, 11(20), eadu9368.

Bartlett, F. C. (1932).

*Remembering: A study in experimental and social psychology*. Cambridge
University Press.

Berger, J., Cohen, B. P., & Zelditch, M., Jr. (1972). Status
characteristics and social interaction.

*American Sociological Review*, 37(3), 241--255.

Berger, J., Fisek, M. H., Norman, R. Z., & Zelditch, M., Jr. (1977).

*Status characteristics and social interaction: An expectation-states
approach*. Elsevier.

Bond, R. M., Fariss, C. J., Jones, J. J., Kramer, A. D. I., Marlow, C.,
Settle, J. E., & Fowler, J. H. (2012). A 61-million-person experiment in
social influence and political mobilization.

*Nature*, 489, 295--298.

Borgatti, S. P., & Foster, P. C. (2003). The network paradigm in
organizational research: A review and typology.

*Journal of Management*, 29(6), 991--1013.

Brashears, M. E., & Gladstone, E. (2016). Error correction mechanisms in
social networks can reduce accuracy and encourage innovation.

*Social Networks*, 44, 22--35.

Brinkmann, L., Baumann, F., Bonnefon, J. F., Derex, M., Müller, T. F.,
Nussberger, A. M., ... & Rahwan, I. (2023). Machine culture.

*Nature Human Behaviour*, 7, 1855--1868.

Burt, R. S. (1992).

*Structural holes: The social structure of competition*. Harvard
University Press.

Carley, K. (1991). A theory of group stability.

*American Sociological Review*, 56, 331--354.

Centola, D. (2010). The spread of behavior in an online social network
experiment.

*Science*, 329, 1194--1197.

Centola, D. (2011). An experimental study of homophily in the adoption
of health behavior.

*Science*, 334, 1269--1272.

Centola, D., & Macy, M. W. (2007). Complex contagions and the weakness
of long ties.

*American Journal of Sociology*, 113(3), 702--734.

Coleman, J. S., Katz, E., & Menzel, H. (1966).

*Medical innovation: A diffusion study*. Bobbs-Merrill.

Gladstone, E. (2016).

*Error in information diffusion processes* \[Doctoral dissertation,
Cornell University\].

Granovetter, M. S. (1973). The strength of weak ties.

*American Journal of Sociology*, 78(6), 1360--1380.

Hancock, J. T., Naaman, M., & Levy, K. (2020). AI-mediated
communication: Definition, research agenda, and ethical considerations.

*Journal of Computer-Mediated Communication*, 25(1), 89--100.

Lin, X., Ning, Y., Zhang, J., Dong, Y., Liu, Y., Wu, Y., Qi, X., Sun, N.,
Shang, Y., Wang, K., Cao, P., Wang, Q., Zou, L., Chen, X., Zhou, C., Wu, J.,
Zhang, P., Wen, Q., Pan, S., Wang, B., Cao, Y., Chen, K., Hu, S., & Guo, L.
(2025). LLM-based agents suffer from hallucinations: A survey of taxonomy,
methods, and directions.

*arXiv preprint arXiv:2509.18970*.

Mohamed, A., Geng, M., Vazirgiannis, M., & Shang, G. (2025). LLM as a
broken telephone: Iterative generation distorts information. In

*Proceedings of the 63rd Annual Meeting of the Association for
Computational Linguistics*.

Ost, J., Blank, H., Davies, J., Jones, G., Lambert, K., & Salmon, K.
(2022). The serial reproduction of an urban myth: Revisiting Bartlett\'s
schema theory.

*Memory*, 30(9), 1123--1136.

Perez, J., Kovač, G., Léger, C., Kouwenhoven, M., Goupil, L.,
Moulin-Frier, C., & Oudeyer, P. Y. (2024). Analyzing text properties
evolution in rephrasing, continuation, and inspiration-taking tasks. In

*Proceedings of the 2024 Conference on Empirical Methods in Natural
Language Processing*.

Podolny, J. M. (2001). Networks as the pipes and prisms of the market.

*American Journal of Sociology*, 107(1), 33--60.

Rodriguez, M. G., Leskovec, J., Balduzzi, D., & Scholkopf, B. (2014).
Uncovering the structure and temporal dynamics of information
propagation.

*Network Science*, 2, 26--65.

Ryan, B., & Gross, N. C. (1943). The diffusion of hybrid seed corn in
two Iowa communities.

*Rural Sociology*, 8, 15--24.

Schaefer, D. R. (2007). Votes, favors, toys, and ideas: The effect of
resource characteristics on power in exchange networks.

*Sociological Focus*, 40, 138--160.

Shannon, C. E. (1950). Prediction and entropy of printed English.

*Bell System Technical Journal*, 30, 50--64.

Sperber, D. (1985).

*Anthropology and psychology: Towards an epidemiology of
representations*. Man, 20(1), 73--89.

Sundar, S. S. (2020). Rise of machine agency: A framework for studying
the psychology of human--AI interaction.

*Journal of Computer-Mediated Communication*, 25(1), 74--88.

Sur, S., Chattopadhyay, R., Claussen, J. C., & Mukhopadhyay, A. (2025).
A mathematical framework for misinformation propagation in complex networks:
Topology-dependent distortion and control.

*arXiv preprint arXiv:2512.19465*.

Tran, K. T., Dao, D., Nguyen, M. D., Pham, Q. V., O\'Sullivan, B., &
Nguyen, H. D. (2025). Multi-agent collaboration mechanisms: A survey of
LLMs.

*arXiv preprint arXiv:2501.06322*.

Wang, D. J., & Soule, S. A. (2012). Social movement organizational
collaboration: Networks of learning and the diffusion of protest
tactics, 1960--1995.

*American Journal of Sociology*, 117, 1674--1722.

Watts, D. J., & Strogatz, S. H. (1998). Collective dynamics of
\'small-world\' networks.

*Nature*, 393, 440--442.

Yax, N., Léger, C., Perez, J., & Oudeyer, P. Y. (2025). When LLMs play
the telephone game: Cumulative changes and attractors in iterated
cultural transmission. In

*Proceedings of the 13th International Conference on Learning
Representations*.

# A Domain-Independent Ontology Learning Method based on Transfer Learning
This project is about a state-of-art ontology learning method to learn ontology from Web pages with a small amount of in-domain training data. We attempt to introduce transfer learning to ontology learning to solve the following problems in current ontology learning methods:

- 1)Current pattern-based ontology learning methods are domain-independent but with a low effect, because they mainly focus on learning ontology from texts and ignore the semi-structured data in the Web.
	

- 2)Current ontology learning methods, based on traditional machine learning, consider both textual and semi-structured data information in the Web, but they are domain-dependent, which means humans need to label a lot of training data for new domains to train models.

We think introducing transfer learning can solve these two problems at the same time, because:

- 1)	Like traditional machine learning algorithms, transfer learning algorithms are feature-based, so they can utilize both textual and semi-structured information in Web pages by defining different features.

- 2)	Different from traditional machine learning, transfer learning aims at learning knowledge from out-of-domains. Therefore, when applying transfer learning algorithms to build learning models for a new domain, people only need to label far less data than using traditional ones.


To validate our method, we collect data from four domains: 
- 1)	Wiki pages of the Fortune Global 500 firms (shorted by CM);
- 2)	Computer science researchers’ profiles pages (shorted by P);
- 3)	Famous computer science conferences’ pages (shorted by CF);
- 4)	Famous computer science journals’ pages (shorted by J). 

Each domain contains 50 Web sites, and we upload some of them in (<a href="https://github.com/OntologyLearning/TransferLearning/tree/master/RawWebPage" title="Title">Web pages</a>). 

Our method contains 3 steps:


- 1)	We first introduce VIPS algorithm [1] to segment a Web page to text units, and then build a vision tree to organize these units according to web vision. In the vision tree, all these units are stored separately in leaf nodes. Inner nodes in vision tree reflect structure information among their children, which means children of an inner node may have some similarities in visions or semantics. We give a running example to explain this process (<a href="https://github.com/OntologyLearning/TransferLearning/tree/master/Running%20Examples" title="Title">Running Expample of VIPS Algorithm</a>). And we also upload some vision tree in (<a href="https://github.com/OntologyLearning/TransferLearning/tree/master/VisionTree" title="Title">VIPS Result</a>), which are organized in extensible markup language (xml).
- 2)	In the second step, terms, which are the concepts and instances in the corresponding ontology, are recognized from these units by TF-Mnt. For a new domain, TF-Mnt will automatically select a proper previous domain based on the domain similarity measured by the correlation coefficient and then constructs transfer knowledge by combining knowledge learned from the previous domain with domain similarity, and domain knowledge by training little labeled data in the new domain. To construct TF-Mnt, we first define some features in this four domain (<a href="https://github.com/OntologyLearning/TransferLearning/tree/master/Features" title="Title">Defined Feature</a>), and then label some data for validataion (<a href="https://github.com/OntologyLearning/TransferLearning/tree/master/LabeledByExperts" title="Title">Labeled Data</a>).
- 3) In the third step, _is-a_ and _subclass-of_ relations between concepts and instances are captured by analyzing the visual structures of the Web page (<a href="https://github.com/OntologyLearning/TransferLearning/tree/master/Running%20Examples" title="Title">Running Example of Relations Learning</a>). With terms and relations, ontology of a Web page can be finally constructed by decoding them in Resource Description Framework (RDF) language(<a href="https://github.com/OntologyLearning/TransferLearning/tree/master/Final%20Ontology" title="Title">Final Ontologies</a>).




_[1]	Deng Cai, Shipeng Yu, Ji-Rong Wen and Wei-Ying Ma. VIPS: a Vision-based Page Segmentation Algorithm. Microsoft Technical Report, 2003._

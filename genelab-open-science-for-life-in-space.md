# GeneLab: Open Science for Life in Space

GeneLab is an interactive, open-access resource where scientists can upload, download, store, search, share, transfer, and analyze omics data from spaceflight and corresponding analogue experiments. Users can explore GeneLab datasets in the [Data Repository](https://osdr.nasa.gov/bio/repo/search?q=\&data\_source=cgene,alsda\&data\_type=study), analyze data using the [Analysis Platform](https://galaxy.genelab.nasa.gov/), and create collaborative projects using the [Collaborative Workspace](https://osdr.nasa.gov/bio/workspace-sso-login.html). GeneLab promises to facilitate and improve information sharing, foster innovation, and increase the pace of scientific discovery from extremely rare and valuable space biology experiments. Discoveries made using GeneLab [have begun](.gitbook/assets/publications) and will continue to deepen our understanding of biology, advance the field of genomics, and help to discover cures for diseases, create better diagnostic tools, and ultimately allow astronauts to better withstand the rigors of long-duration spaceflight.

GeneLab helps scientists understand how the fundamental building blocks of life itself – DNA, RNA, proteins, and metabolites – change from exposure to microgravity, radiation, and other aspects of the space environment. GeneLab does so by providing fully coordinated epigenomics, genomics, transcriptomics, proteomics, and metabolomics data alongside essential metadata describing each spaceflight and space-relevant experiment. By carefully curating and implementing best practices for data standards, users can combine individual GeneLab datasets to gain new, comprehensive insights about the effects of spaceflight on biology. In this way, GeneLab extends the scientific knowledge gained from each biological experiment conducted in space, allowing scientists from around the world to make novel discoveries and develop new hypotheses from these priceless data.

### Why Experiments in Space Matter

To explore deeper into space, it is crucial that we learn how our bodies change and adapt to the unique environment of space. Scientists have been studying the effects of space exploration on the physiology of humans since the first launch of astronauts into space over 50 years ago. Since then, we have discovered that the human body behaves differently in space: wounds heal slower, bones grow thinner, fluid shifts lead to intracranial pressure and visual impairment, and there are notable changes in our immune and cardiovascular functions. Underlying all of these changes are alterations to the transcriptional patterns and molecular signaling networks induced by spaceflight. Such changes lead to health risks for astronauts that must be understood and mitigated in order to live and work in space for longer periods of time.

Similar to life science research conducted on Earth, animal models play a critical role in our understanding of how spaceflight affects humans. Small animals such as _Drosophila_ are useful as they have short lifespans, allowing us to study the molecular effects of spaceflight over multiple generations; produce large populations, which enhances the statistical power of _Drosophila_ studies; and about half of all fruit fly (_D. melanogaster_) genes have orthologs to one or more human genes, including genes involved in development and cardiovascular diseases. Mammals, such as mice and rats, contain several more human orthologs and thus are better models to recapitulate the physiological changes observed in humans, although they are limited due to their longer life cycle and small cohort size. Therefore, collecting data from various animal models flown in space is an important aspect of GeneLab and will allow users to capture a complete picture of the molecular changes associated with space.

Biological space research also promotes the health and well-being of humans here on earth. Various diseases and nuances that exist on Earth such as osteoporosis, heart disease, loss of visual acuity, and the emergence of virulent microbes seem to be accelerated in space. Studying the molecular underpinnings of disease progression during spaceflight can provide insight to the onset of similar diseases on Earth and advance our understanding and subsequently our ability to detect and successfully treat such diseases.

The microgravity environment and heightened exposure to damaging radiation also effects microbes present in space. Learning how these species change on the molecular level in response to spaceflight will allow us to understand what potential threats they may pose to astronauts. Such knowledge also has direct applications on earth including paving the way for more effective treatments to combat harmful microbes. In addition, the growing field of microbiota is changing how we look at life, clearly illustrating the synergism between microbes and their hosts (animals or plants). The information gained from analyzing how the combined genetic material of microorganisms change in the space environment (i.e. microbiome), both inside and outside a host, will allow us to engineer them to become more efficient at aiding our digestion, safely decomposing waste, enhancing plant biology through symbiosis, and to become effective microbial factories.

Lastly, to become a multi-planet species, humans must learn how plants adapt to space as well as environments different from our own in order to grow and cultivate plants in all environments humans may one day inhabit. The microgravity of spaceflight provides plant biologists with a tool to further characterize the mechanisms that govern gravitropic and phototropic responses in plants. Insight into the differences in gene expression of plants grown in microgravity can help us understand the fundamental mechanisms of cell biology. Furthermore, the discoveries made in space can be used to generate more nutritious and robust plants to support an ever-growing population here on Earth.

### International Space Station

The [ISS](https://www.nasa.gov/mission\_pages/station/main/index.html) is the largest human-made structure in low Earth orbit (LEO) and serves as a space environment research laboratory where astronauts perform experiments in several unique fields including physics, astronomy, and biology. The biological studies conducted on the ISS generate critical data that scientists use to determine how terrestrial biology changes as a result of spaceflight. The outcomes of those experiments will be used to enable humans to explore deeper into space and eventually pave the way for humans to become an interplanetary species.

Humans have been in space continuously since 2000 thanks to our home in LEO and over the past almost two decades, the ISS has enabled significant discoveries and advances. From enhancing our ability to predict weather patterns to becoming almost as efficient as our kidneys at conserving water (about 70% of water aboard the ISS is recovered), the ISS has led to new technologies that will continue to push the limits of our species. Now, with the help of GeneLab, biological experiments conducted aboard the ISS will reach a greater scientific audience and continue to shape our understanding of the universe on both a macro and micro scale.

### Where Do GeneLab’s Datasets Come From?

**GeneLab is the first comprehensive database in the world that hosts a growing collection of omics data generated from spaceflight and spaceflight analogue experiments.** GeneLab’s database is a collection of information from biological experiments that date as far back as 1995 through current studies conducted aboard the ISS and other platforms like the retired space shuttle program.

There are three main avenues used to acquire the data that are ultimately hosted on GeneLab: 1) mining the literature and other public databases including the National Institutes of Health (NIH) Gene Expression Omnibus (GEO), European Bioinformatics Institute (EBI) Proteomics Identification (PRIDE), and Argonne National Laboratory (ANL) Metagenomics Rapid Annotations using Subsystems Technology (MG-RAST), 2) direct uploads to GeneLab by scientists conducting space-relevant experiments, and 3) data generated by GeneLab using our state-of-the-art Sample Processing Lab (SPL). For the third avenue, samples are acquired by requesting unused tissues and samples from experiments conducted in space through the [Biospecimen Sharing Program](https://science.nasa.gov/biological-physical/space-biology-biospecimen-sharing-program) and [Life Sciences Data Archive](https://lsda.jsc.nasa.gov/).

To maximize the scientific return of every biological spaceflight experiment, the GeneLab SPL uses specialized protocols to process the unused samples returned to Earth from space. All of the standard protocols used for nucleic acid (and protein) extraction, library preparation, and sequencing were established in collaboration with the scientific community. For consistency across experiments, once a protocol is established and verified for a particular tissue type, that same protocol is performed for every sample from every experiment containing that tissue type. This approach guarantees greater accuracy when comparing datasets from different spaceflight experiments and GeneLab encourages the space biology community to follow similar standards.

Most raw data hosted on GeneLab are processed using [standard pipelines](https://github.com/nasa/GeneLab\_Data\_Processing) that were established in collaboration with the greater scientific community (i.e. GeneLab’s [Analysis Working Group](https://osdr.nasa.gov/bio/awg/charter.html)) and the processed data are made available on the [GeneLab repository](https://osdr.nasa.gov/bio/repo/search?q=\&data\_source=cgene,alsda\&data\_type=study). Processing these data in a consistent manner allows for more accurate comparisons of historic spaceflight data with recently generated data, and comparison of spaceflight analogue experiments with actual spaceflight data.

All datasets hosted on GeneLab are carefully curated to include all essential metadata associated with each experiment. The meticulous curation and organization of data hosted on GeneLab allows users to easily navigate the datasets and identify key information necessary for accurate interpretation of results.

### Can GeneLab Host My Data?

All scientists performing space-relevant research are welcome and encouraged to [**submit data**](https://osdr.nasa.gov/bio/submission-sso-login.html) to be hosted on GeneLab. Once the raw data are uploaded to GeneLab, the data processing team will analyze it using established pipelines and make the processed data available to the public. Not sure if your data is consistent with the goals of GeneLab? [Just ask](https://osdr.nasa.gov/bio/help/contact.html).

### What Types of Data are Available?

GeneLab provides raw microarray, RNA-sequencing, bisulfite-sequencing, proteomic, metabolomic, and metagenomic data from spaceflight and spaceflight-relevant biological experiments, including microbe, plant, and animal studies. Because raw omics data can be large and lack biological meaning, the processed data products generated from each step of the analysis pipeline for RNAseq, microarray, amplicon (16S) sequencing, and bisulfite sequencing are also made available to the public. This allows for transparency across the GeneLab platform and makes these priceless datasets accessible to scientists at every level. Furthermore, by publishing every data product generated from each step of our standard pipelines, scientists who want to learn bioinformatics are able to follow along our publicly available pipelines and compare their data products to GeneLab’s. Additionally, these intermediate data products allow for the flexibility to pick up the data at any step in the pipeline and analyze it using a different tool without having to start from the raw data. As with our standard Sample Processing Lab protocols, implementing standard pipelines for each assay type allows for easier and more accurate comparisons across different experiments and tissue types.

### Funding

GeneLab is funded by [NASA’s Division of Biological and Physical Sciences (BPS)](https://science.nasa.gov/biological-physical), which provides administrative oversight of NASA's Biological and Physical Sciences Research that focuses on using the spaceflight environment to enable space exploration and benefit life on Earth.

### The GeneLab Community

Good science is never done alone. The primary goal of GeneLab is to bring together a community of scientists to utilize the spaceflight and spaceflight analogue datasets hosted on GeneLab to generate novel discoveries and hypothesis-driven, collaborative, follow-on investigations. To achieve this goal and to ensure that GeneLab is using the most relevant and up-to-date sample processing, library preparation, high-throughput sequencing, and data analysis protocols and pipelines, the GeneLab [Analysis Working Group ](https://osdr.nasa.gov/bio/awg/charter.html)(AWG) has been established. The AWG is composed of scientists with diverse backgrounds across government, industry, and academia and is subdivided into four main groups (or areas of expertise) including plants, animals, microbes, and multi-omics/systems biology. GeneLab AWG members meet regularly to help establish consensus pipelines, discuss processed data generated from those pipelines, and analyze GeneLab data, which leads to [published manuscripts](.gitbook/assets/publications) summarizing new discoveries. The AWG also ensures that GeneLab products are in line with the needs of the greater scientific community. Anyone interested in space-relevant data with an understanding of omics or those who want to help keep GeneLab relevant are welcome to [join the AWG](https://osdr.nasa.gov/bio/awg/join.html).

GeneLab also works in collaboration with other NASA centers, including Johnson Space Center, Kennedy Space Center, and the Jet Propulsion Laboratory, and welcomes international collaborations with space agencies outside the US. If you’re interested in becoming part of the GeneLab community, contact us.
# environmentalSoundHdf

Python module for summarizing environmental sound and metadata for scientific analysis.

**If you are thinking about how you or your workgroup should store a large amount of sound data for subsequent analysis, then this module could be the answer. The module also provides methods to work with this data directly with the >opensoundscape< module for analysis.**

## Typical use cases and usefulness of a software solution for which the Python module will be made

### Environmental sound recording

Environmental sound recording is a frequently used application in field research to detect the presence of species in a certain area or to monitor their presence in the long term if they make themselves heard. This is common for the group of birds (also night bird migration), for bats and sometimes for acoustically active insects such as cicadas. In areas where other animal groups, such as monkeys, also frequently make their presence and activity known through vocalizations, these methods can also be used for such animal groups.

### Additional data acquisition

The objectives of field research can vary considerably, which is why it can be necessary and is common practice to collect additional information alongside the sound data. In the following, this data is called ‘metadata’, although it can be more valuable in terms of content than simply providing context for the sound data. However, as the core of the module is essentially used to summarize sound data, we will continue to use the term ‘metadata’ for this data. This generally and commonly includes weather data, current light brightness, e.g. the actual twilight brightness at the location of the sound recording. Particularly in the vicinity of breeding sites, however, movement data of individuals is also of interest and must be recorded in synchronization with the sound. This means that these metadata are not always just simple attributes of the sound data, but can result in completely independent data series. Although in many cases the metadata actually represent little more than attributes of the sound data, we would at least like to leave open the possibility here that metadata can also be time-stamped information that occurs in parallel to the sound data.

### Pragmatic solutions, their problems and the aim of the project

Not every scientific working group has the opportunity to appoint an experienced software-savvy data specialist as a member of their group. Depending on the experience of the members of the working group, pragmatic solutions are chosen to summarize the data from the data recorders. The primary, minimum goal is to summarize the data in such a way that it can be used for at least a single analysis with subsequent publication of findings. The consequence of this is that the data is lost for subsequent use at a later date or by other working groups if at least one member of the original working group is not available to help interpret the data files. This is a common and recurring problem in science.

While openly accessible and well-documented software tools are usually used for the actual evaluation of the data, it is rather difficult to access and extract the data from the collected data series themselves due to the pragmatic isolated solutions often practiced as described above.

There are now good examples where such mass data series can be stored in a format that provides the desired conditions for reusability of the data. In the field of artificial intelligence, the need for well-structured mass data has become established and has led to solutions such as Pandas, which actually enable the data to be reused beyond the working group that generated it.

However, data sampled in great detail over time, such as environmental audio data, has special requirements, as this data is usually not fed to AI applications as a pure data series, but is selected and pre-processed in pre-processing phases and sometimes converted into completely different mathematical spaces. All the more so if metadata containing more information than a simple singular attribute for a sound data series over a specific time range is also recorded in parallel.

This project is intended to address precisely this specificity in order to ensure the implementation of ‘good scientific practice’ (publication of source data in parallel with the publication of results obtained from it) for scientific data series with the content character described above, but also to provide working groups with limited resources with tools for data structuring in addition to the analysis tools that are usually available.

### What is the right data format for audio and meta data?

First of all: This project specialises in sound records. Recordings of all other data are useful and often important. But we interpret sound data as primary data and all other recorded data as secondary ‘metadata’. There is of course no reason to reduce the content of this metadata to simple attributes if this data is not specifically recorded to be truly only metadata in the sense of attributes. However, this means that we concentrate on preparing our interfaces in such a way that they are particularly well suited for use with opensoundscape:

> Opensoundscape is the leading Python project for processing environmental audio data.

## Databases for use with sample recording data

> The core question is, how we should save our data to be optimal usable?

### Sound files

This is the common way in case there are not really special requirements.

#### What about the file order?

... [Work in progress]

#### What about the meta data?

... [Work in progress]

## Project State

Development for a first version with a reasonable range of functions in progress.

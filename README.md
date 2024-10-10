# wildlifeRecords2Hdf (Python module)

Python module for summarizing environmental sound (image) and metadata for scientific analysis.

> **Framework with methods for organising mass source data, in particular environmental sound recordings or wildlife camera images, including other recorded data that is directly related to this mass source data, in such a way that the data can be easily accessed at any later point in time. The magic words are "self-describing database".**

**If you are thinking about how you or your workgroup should store a large amount of sound or/and image data for subsequent analysis,** then this module could be the answer. The module also provides methods to work with this data directly with the [opensoundscape](https://opensoundscape.org) module for analysis.

## Typical use cases for which the Python module will be made

### Environmental sound recording

Environmental sound recording is a frequently used application in field research to detect the presence of species in a certain area or to monitor their presence in the long term if they make themselves heard. This is common for the group of birds (also night bird migration), for bats and sometimes for acoustically active insects such as cicadas. In areas where other animal groups, such as monkeys, also frequently make their presence and activity known through vocalizations, these methods can also be used for such animal groups.

A 24/7 recording will yield a lot of sample data. For bird calls and songs as example, up to 12 kHz and 4-fold oversampling is useful, so 48 kS/s and a resolution of 16 bits would be a good choice: The data volume per month is 1/4 TByte. It is commen that recorder systems split the data into smaller chunks to protect it against a variety of error cases, from write errors to power outages. Splitting into 15-minute chunks would give you 86.4 MB per file and 2880 files per month. With two-channel audio for better extraction of simultaneously calling or singing individuals (as a later pre-processing step), it results in half a terrabyte per month and field recorder. This data volume is of course somewhat lower if specialised devices such as AudioMoth are used, which can only record time segments across the day.For 24/7 recording you get a lot of sampling data. For bird calls, as example, until 12kHz and 4 times oversampling, 48kS/s and 16Bit resolution is a good choice. You get 250GB per month and channel. Typical recorder configurations split the data in smaller chunks to be save in different cases from write erros until power-of scenarios. 15 minutes chunks would have 86.4MB per file and 2880 files per month. In the case of 2-channel-audio, for a better individuen extraction as preprocessing, we get a half Terrabyte per Month per field recorder. This amount of data is smaller in case of using soecial devices, like AudioMoth, what can record only time slices over each day.

At the latest when you use several such field recorders and perhaps also want to combine the data with metadata, such as the current weather, the question arises as to how this data can be meaningfully merged and stored. This is especially true if you want to preserve the data for future tasks.At the latest when you use several such field recorders and perhaps also want to combine the data with metadata, such as the current weather, the question arises as to how you can reasonably bring together and store this data

### Additional data acquisition

The objectives of field research can vary considerably, which is why it can be necessary and is common practice to collect additional information alongside the sound data. In the following, this data is called ‘metadata’, although it can be more valuable in terms of content than simply providing context for the sound data. However, as the core of the module is essentially used to summarize sound data, we will continue to use the term ‘metadata’ for this data. This generally and commonly includes weather data, current light brightness, e.g. the actual twilight brightness at the location of the sound recording. Particularly near breeding sites, however, movement data of individuals is also of interest and must be recorded synchronously with the sound and possibly also in parallel with recordings from image recording devices. This means that these metadata are not always just simple attributes of the sound data, but can result in completely independent data series. Although in many cases the metadata actually represent little more than attributes of the sound data, we would at least like to leave open the possibility here that metadata can also be time-stamped information that occurs in parallel to the sound data.

### Pragmatic solutions, their problems and the aim of the project

Not every scientific working group has the opportunity to appoint an experienced software-savvy data specialist as a member of their group. Depending on the experience of the members of the working group, pragmatic solutions are chosen to summarize the data from the data recorders. The primary, minimum goal is to summarize the data in such a way that it can be used for at least a single analysis with subsequent publication of findings. The consequence of this is that the data is lost for subsequent use at a later date or by other working groups if not at least one member of the original working group is not available to help interpret the data files. This is a common and recurring problem in science.

While openly accessible and well-documented software tools are usually used for the actual evaluation of the data, it is rather difficult to access the source data again later and extract it from the collected data series due to the pragmatic isolated solutions described above.

There are now good examples where such mass data series can be stored in a format that provides the desired conditions for reusability of the data. In the field of artificial intelligence, the need for well-structured mass data has become established and has led to solutions such as Pandas, which actually enable the data to be reused beyond the working group that generated it.

However, data sampled in great detail over time, such as environmental audio data, has special requirements, as this data is usually not fed to AI applications as a pure data series, but is selected and pre-processed in pre-processing phases and sometimes converted into completely different mathematical spaces. All the more so if metadata containing more information than a simple singular attribute for a sound data series over a specific time range is also recorded in parallel.

This project is intended to address precisely this specificity in order to ensure the implementation of ‘good scientific practice’ (publication of source data in parallel with the publication of results obtained from it) for scientific data series with the content character described above, but also to provide working groups with limited resources with tools for data structuring in addition to the analysis tools that are usually available.

### What is the right data format for audio and meta data?

First of all: This project specialises in sound records. Recordings of all other data are useful and often important. But we interpret sound data as primary data and all other recorded data as secondary "metadata". There is of course no reason to reduce the content of this metadata to simple attributes if this data is not specifically recorded to be truly only metadata in the sense of attributes. However, this means that we concentrate on preparing our interfaces in such a way that they are particularly well suited for use with opensoundscape:

> **Opensoundscape is the leading Python project for processing environmental audio data.**

### Images as meta or main data

With regard to the question of metadata, image data plays a special role, however, since it can also be available as mass data and, in the context of audio data, it must also undergo similarly complex recognition algorithms. For this reason, it is planned at a later point in time to also organise image data within this framework in a comparable way and to organise it together with audio data in a common database.

## Databases for use with fine-sampled recording data

> **The core question over all is, how we should save our data to be optimal usable?**


## Project State

Development for a first version with a reasonable range of functions in progress.

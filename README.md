# User-aided Pattern Search and Analysis on Business Graphs
Bachelor's thesis at HPI Potsdam

## [Final PDF](/ba-milan-gruner.pdf)

## Abstract
> Costructing a graph made up of thousands of businesses may be hard, but actually making sense of it is a lot harder.
> With huge amounts of data potentially being integrated into the data lake every day, automatic methods for finding interesting spots in the graph are needed.
> This paper discusses different approaches that can be taken to extract useful knowledge from such a graph.

## Introduction
    This paper describes the basic approach of Pattern Search and Analysis
    on the graphs generated as a part of the Ingestion bachelor project at HPI Potsdam.
    It deals with the experiments I performed to evaluate certain algorithms and approaches to summarize
    automatically generated graphs in the ball park of tens of millions of nodes in
    a large and mostly unconnected and sparse graph.
    It contains businesses, places and persons and can be augmented freely by adding
    additional data sources (or manual data input) of your own. The data is visualized and controllable from the
    Curation interface, which was a project developed alongside the Ingestion pipeline.
    Curation generates graphs on-the-fly that contain the statistics data that was written
    as a side effect of the numerous Spark jobs in the Ingestion pipeline and gives
    a lot of insight into what's going on in the "data lake".
    All of the experiments contained in this paper were conducted using either
    the Curation interface, the Apache Zeppelin interactive web shell or the Spark shell.

    Most of the topics in this paper deal with graph-related topics, so the Spark GraphX framework
    (in Scala) will mostly be used to describe the algorithms that were employed,
    but it can be freely seen as functional pseudo code and adapted to other popular
    graph processing frameworks (such as Giraph etc.) % TODO more examples
    For UI-related or user-oriented algorithms, JavaScript (or JSX, so partly using React/ Redux etc.)
    is the listing language, as visual problems are more easily expressed in this
    tree-oriented but still functional style (and also because it's used in Curation). % TODO remove?
    Whereever possible, ES2016 Syntax is used for the brevity and the similarity
    to the functional approach of Scala and the rest of the example code.

    Also one of the purposes of the Ingestion and Curation projects was to enable
    the execution of modern text mining, deduplication and parallel data analysis
    to the german business landscape. This means that some of the examples will be
    in German (but they will be translated if needed for understanding the technique).

# Documentation

## Data processing pipeline

{% mermaid %}

graph TD;

t\[transducer\]

m\(\(medium\)\)

a\[variable gain amplifier\]

f\[bandpass filter\]

d\[digitalization\]

e\[envelope detection\]

c\[scan conversion\]

l\[display\]



subgraph device

t--&gt;a

a--&gt;f

f--&gt;d

end



subgraph smartphone 

e--&gt;c

c--&gt;l

end



d-.wifi.-&gt;e

m-.ultrasound &lt;br/&gt; propagation.-&gt;t



{% endmermaid %}








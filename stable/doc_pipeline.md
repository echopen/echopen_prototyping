# Documentation

## Data processing pipeline

{% mermaid %}
graph TD;

t[transducer]
m((medium))
a[variable gain amplifier]
f[bandpass filter]
d[digitalization]
e[envelope detection]
c[scan conversion]
l[display]

subgraph device
t-->a
a-->f
f-->d
end



subgraph smartphone 
e-->c
c-->l
end

d-.wifi.->e
m-.ultrasound <br/>; propagation.->t

{% endmermaid %}








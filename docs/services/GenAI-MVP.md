# GenAI MVP experiment
## Performance testing
Testing VLLM instead of OLLAMA
Performance optimization with quantization
Currently running on a 2-GPU server at Hetzner
Requires 20 GB VRAM – therefore it cannot run on Azure (only has 16 GB)!
![Screenshot from performance test](img/Time to first token 1.jpg)
1 server (system prompt response set to min. 50-150 words)
– handles up to 250 simultaneous requests
– breaks at 180
Response time – 0-60 sec.
Time to frist token 2
1 server
Max response time vs. number of requests
If we can accept up to 4 sec. response time for the first token, 1 server can handle approximately 180 requests at a time. Multiply the number with the number of servers: 2 servers = 360 simultaneous users.
Time to first token 3
With 2 servers – 380 simultaneous users, max response time of 4.5 sec. for the first token.
Time to frist token 4
Comparison between AQW and GPTQ and without quantization at 380 simultaneous users.
At 500 simultaneous users (GPTQ) – response time up to 7 sec., but we still respond!
Time to first token 5

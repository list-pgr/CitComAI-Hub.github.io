# GenAI MVP experiment
GovTechMidtjylland has conducted a GenAI pilot experiment to investigate:\
1: what does it take for a munucipality to develop, run and implement a GenAI in a public context?
2: which usecases can benefit from a GenAI solution?

The GenAI repo can be reviewed here: https://github.com/itk-dev/ai-launchpad

## Performance testing
As part of the implementation, a performance test was conducted:

Testing VLLM instead of OLLAMA\
Performance optimization with quantization\
Currently running on a 2-GPU server at Hetzner\
Requires 20 GB VRAM – therefore it cannot run on Azure (only has 16 GB)!\
![Screenshot](/docs/services/img/Time_to_first_token_1.jpg)\
1 server (system prompt response set to min. 50-150 words)\
– handles up to 250 simultaneous requests\
– breaks at 180\
Response time – 0-60 sec.\
![Screenshot](/docs/services/img/Time_to_first_token_2.jpg)\
1 server\
Max response time vs. number of requests\
If we can accept up to 4 sec. response time for the first token, 1 server can handle approximately 180 requests at a time. Multiply the number with the number of servers: 2 servers = 360 simultaneous users.\
**Time to first token 3**\
With 2 servers – 380 simultaneous users, max response time of 4.5 sec. for the first token.\
**Time to frist token 4**\
Comparison between AQW and GPTQ and without quantization at 380 simultaneous users.\
At 500 simultaneous users (GPTQ) – response time up to 7 sec., but we still respond!\
**Time to first token 5**

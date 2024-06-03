# Poem-Generation-Project-v2
A text generation initiative employing web data crawling and GPT-2 transformer architecture to compose Vietnamese poetry.

# Dataset
Taking Haiku poetry data from first 10 pages at https://www.thivien.net/searchpoem.php?PoemType=16&ViewType=1&Country=2 

# Progamming languages and Technologies
Languages: Python
Technologies: pandas, datasets, pytorch, transformers, huggingface_hub

# Inference
```python
prompt = 'Học học nữa học mãi\n'
device = 'cuda' if torch.cuda.is_available() else 'cpu'
inputs = tokenizer(prompt, return_tensors="pt").input_ids.to(device)
outputs = model.generate(
    inputs,
    max_new_tokens=50,
    do_sample=True,
    top_k=50,
    top_p=0.95,
    temperature=0.8,
    repetition_penalty=1.2
)
results = tokenizer.batch_decode(outputs, skip_special_tokens=True)
results = results[0]
print()
for line in results.split('\n'):
    print(line)
```

```
Học học nữa học mãi
Hàng trăm ngàn đêm dài
Nhưng, không ai quên
Quanh ta thấy chuyện? đỏ?
Tôi thấy mình là học giả!
Đôi hay bạc đau may chờ.
Còn để ra mắt nào nữa?
Vì, ta thấy bạn
```







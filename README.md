# Automata Embedding Data Repository

This repository contains the pre-generated embedding data used in the Automata project. The Automata project requires embeddings for various aspects of its operation, and these are kept in this repository for easy management and versioning.

The embeddings are stored in a `ChromaSymbolEmbeddingVectorDatabase`, which is a customized data store based on the Chroma vector database. This database stores key-value pairs, where the key is a symbol from the codebase and the value is an embedding vector that represents this symbol in a high-dimensional space. 

## Usage

This repository is included as a Git submodule in the main Automata repository. To include the embeddings in your local copy of Automata, clone the repository with the `--recurse-submodules` option:

```bash
git clone --recurse-submodules https://github.com/emrgnt-cmplxty/automata.git
```

If you've already cloned the repository, you can fetch the submodule with:

```bash
git submodule update --init --recursive
```

In the Automata code, the embeddings are accessed using the `ChromaSymbolEmbeddingVectorDatabase` class. For example, to get an embedding for a particular symbol, use the `get()` method:

```python
key = parse_symbol('your_symbol_here')
embedding = embedding_database.get(key)
```

You can also add, update, and batch process entries using the methods provided by `ChromaSymbolEmbeddingVectorDatabase`.

This data repository currently supports the following repositories:

- [**Automata**](https://github.com/emrgnt-cmplxty/Automata) _(automata)_
- [**LlamaIndex**](https://github.com/jerryjliu/llama_index/tree/main) _(llama_index)_
- [**langchain**](https://github.com/hwchase17/langchain) _(langchain)_
- [**chroma**](https://github.com/chroma-core/chroma/tree/main) _(chromadb)_
- [**pandas**](https://github.com/pandas-dev/pandas) _(pandas)_
- [**flask**](https://github.com/pallets/flask) _(src/flask)_
- [**scikit-learn**](https://github.com/scikit-learn/scikit-learn) _(sklearn)_
- [**tensorflow**](https://github.com/tensorflow/tensorflow) _(tensorflow)_
  
In all instances, the embeddings are stored in the collection contained in the parentheses.
## Contributing

We welcome contributions to the embedding data. If you've generated new embeddings that you believe would be useful to the Automata project, please submit a pull request. Be sure to include details about how the embeddings were generated.

Before submitting a pull request, please make sure your changes pass all existing tests. Add new tests for any new functionality or to cover any areas you think are lacking.

For detailed instructions on contributing, please see the [CONTRIBUTING.md](CONTRIBUTING.md) file in the main Automata repository.

## License

The embeddings and associated code are released under the Apache License 2.0. Please see the [LICENSE](LICENSE) file for details.

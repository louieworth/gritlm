# training for test dataset
```
torchrun --nproc_per_node 1 \
-m gritlm.training.run \
--output_dir test_path \
--model_name_or_path openaccess-ai-collective/tiny-mistral \
--train_data gritlm/training/toy_data/toy_data_embedding.jsonl \
--learning_rate 1e-5 \
--num_train_epochs 5 \
--per_device_train_batch_size 2 \
--dataloader_drop_last True \
--normalized True \
--temperature 0.02 \
--query_max_len 32 \
--passage_max_len 128 \
--train_group_size 2 \
--mode embedding \
--attn cccc
```
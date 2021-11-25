# swinir_model_compression


# Training
1. Go to KAIR code
2. Modifications
   1. models/model_plain.py
      - What has changed : add sparse_selection function during training
      - Copy/paste model_plain.py
   2. models/network_swinir.py
      - What has changed : add channel_selection function and pruning layer on feed forward network
      - Copy/paste network_swinir_prune.py
   3. options/swinir/train_swinir_sr_classical.json
      - What has changed : change "dist" from true to false (this part handles data parallel)
      - Copy/paste train_swinir_sr_classical.json 
3. Train the model same as before.

# Test
1. Go to SwinIR code
2. Modifications
   1. Copy trained model(.pth) to model_zoo/
   2. models/network_swinir.py
      - Copy/paste network_swinir_prune.py
   3. main_test_swinir.py
      - Copy/paste main_test_swinir_prune.py
  d. Run the test.

A little comment 
  - I do not recommend changing the original code. I said 'copy/paste' for brevity but I strongly recommend making copies of original file before modifying the code. They can be easily mixed up.

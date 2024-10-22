Nested Loop  (cost=19231094.47..19231187.71 rows=31 width=49)
  ->  Unique  (cost=19231093.78..19231097.50 rows=31 width=67)
        InitPlan 1 (returns $1)
          ->  Gather  (cost=1000.00..9611250.26 rows=1 width=67)
                Workers Planned: 9
                ->  Parallel Seq Scan on accounts  (cost=0.00..9610250.16 rows=1 width=67)
                      Filter: (human_readable = 'EQDvRFMYLdxmvY3Tk-cfWMLqDnXF_EclO2Fp4wwj33WhlNFT'::text)
        InitPlan 2 (returns $3)
          ->  Gather  (cost=1000.00..9611250.26 rows=1 width=67)
                Workers Planned: 9
                ->  Parallel Seq Scan on accounts accounts_1  (cost=0.00..9610250.16 rows=1 width=67)
                      Filter: (human_readable = 'EQCcLAW537KnRg_aSPrnQJoyYjOZkzqYp6FVmRUvN1crSazV'::text)
        ->  Gather Merge  (cost=8593.27..8596.91 rows=31 width=67)
              Workers Planned: 1
              Params Evaluated: $1, $3
              ->  Unique  (cost=7593.26..7593.41 rows=31 width=67)
                    ->  Sort  (cost=7593.26..7593.33 rows=31 width=67)
                          Sort Key: nft.owner_account_id
                          ->  Nested Loop  (cost=13.20..7592.49 rows=31 width=67)
                                ->  Parallel Bitmap Heap Scan on get_nft_data nft  (cost=12.64..1262.06 rows=666 width=67)
                                      Recheck Cond: (collection_account_id = ($1)::text)
                                      ->  Bitmap Index Scan on idx_getmethods_get_nft_data_collection_address  (cost=0.00..12.35 rows=1132 width=0)
                                            Index Cond: (collection_account_id = ($1)::text)
                                ->  Index Scan using idx_getmethods_get_wallet_data_owner_address on get_wallet_data jetton  (cost=0.56..9.50 rows=1 width=67)
                                      Index Cond: (owner_account_id = nft.owner_account_id)
                                      Filter: (jetton_account_id = ($3)::text)
  ->  Index Scan using accounts_pkey on accounts a  (cost=0.69..2.91 rows=1 width=116)
        Index Cond: ((id)::text = nft.owner_account_id)
JIT:
  Functions: 22
  Options: Inlining true, Optimization true, Expressions true, Deforming true- 👋 Hi, I’m @jj6788
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
jj6788/jj6788 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

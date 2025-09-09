This repo includes scripting samples for APIM Policy for AOAI Smart Load Balancing

APIM_SmartLB_Unified - SPIM Policy Template for Smart Load Balancing
  This policy will intelligently select the best embedding type first, 
  then consider deployment model, then infrastructure type, creating a realistic and flexible load balancing strategy that prioritizes embedding quality while maintaining cost and performance considerations.
  
      Random Distribution of Embedding Types:
      Interesting Combinations Created:
      
        GPT-5 + ada-002 + PTU (East US) - High model, mid-tier embedding
        GPT-5 + 3-large + PTU (East US 2) - Best of both worlds
        GPT-4.1 + curie-001 + PTU (West US) - High model, legacy embedding
        GPT-4o + 3-small + Zonal (Canada East) - Good balance
        GPT-4o + davinci-001 + Zonal (South Central) - Mixed performance
        GPT-4o-mini + 3-large + Standard (Australia East) - Best embedding, lower model
        GPT-4o-mini + legacy + Standard (France Central) - Both legacy
        GPT-3 + 3-small + Standard (UK South) - Old model, new embedding
        GPT-4.1 + 3-large + Zonal (Japan East) - High-quality combo
        GPT-3 + ada-002 + Standard (Norway East) - Legacy combo
        GPT-4o + legacy + PTU (Switzerland North) - PTU with legacy embedding
        GPT-4o-mini + davinci-001 + Zonal (Brazil South) - Mixed tier
      
      Selection Priority Examples:
      Best Case Scenario:
      
        text-embedding-3-large (Weight: 2000) wins regardless of model
        Examples: East US 2 (GPT-5), Japan East (GPT-4.1), Australia East (GPT-4o-mini)
      
      Interesting Edge Cases:
      
        GPT-5 with ada-002 vs GPT-4o-mini with 3-large → 3-large wins (embedding priority)
        GPT-4.1 PTU with curie-001 vs GPT-4o Zonal with 3-small → 3-small wins (embedding priority)

    Real-World Scenarios This Handles:
    
    Best Performance: Routes to 3-large embeddings first
    Cost Optimization: Falls back through ada-002 → legacy → similarity models
    Geographic Distribution: Multiple regions with different embedding types
    Infrastructure Mix: PTU, Zonal, and Standard deployments all represented
    Model Diversity: Different OpenAI models with various embedding capabilities



The repo also includes initial templating for FinOps showback purposes.

APIM_Showback - Common KQL Queries for showback purposes.
PBI_SchemaDAXMeasures - Power BI Schema and DAX Measures
APIM_AOAI_CustomMetrics - Template APIM Policy for capturing custom metrics for showback purposes with AOAI API calls. 

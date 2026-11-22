# Patient-Level Data Splits

Split data by patient, never by individual slice, to avoid leakage between training and test sets. Record patient counts and class distribution in each partition. Keep the final test cohort untouched until model selection is complete.
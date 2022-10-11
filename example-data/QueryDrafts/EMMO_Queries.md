1. Welche Materialien sind in den Daten vorhanden?
    ```
    PREFIX emmo: "http://emmo.info/emmo#"

    SELECT * WHERE{
        ?material_instance rdf:type emmo:EMMO_4207e895_8b83_4318_996a_72cfb32acd94;         #emmo:Material
    }
    ```
2. Welche Eigenschaften haben die Materialien (oder ein bestimmtes)?
    - z.B. welche Masse haben die vorhandenen Samples?
    - z.B. welche Größe haben die beteiligten gekochten Eier?

    ```
    PREFIX emmo: "http://emmo.info/emmo#"

    SELECT * WHERE{
        ?material_instance rdf:type emmo:EMMO_4207e895_8b83_4318_996a_72cfb32acd94;         #emmo:Material
                emmo:EMMO_e1097637_70d2_4895_973f_2396f04fa204 ?material_property_instance.     #emmo:hasProperty
    }
    ```

3. Welche Prozesse sind in den Daten vorhanden?

        ```
    PREFIX emmo: "http://emmo.info/emmo#"

    SELECT * WHERE{
        ?process_instance rdf:type emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce.         #emmo:Process
               
    }
    ```
4. Welche Prozessschritte (Teilprozesse) gibt es?

        ```
    PREFIX emmo: "http://emmo.info/emmo#"

    SELECT * WHERE{
        ?process_instance rdf:type emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce;         #emmo:Process
               emmo:EMMO_f22abf74_4538_4f50_ab85_09908cdda707
    }
    ```
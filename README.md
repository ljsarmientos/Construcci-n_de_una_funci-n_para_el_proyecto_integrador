 Construcción de una función para el proyecto integrador

 DELIMITER //

CREATE FUNCTION calcular_calificacion_promedio(docente_id INT)
RETURNS FLOAT
BEGIN
    DECLARE promedio FLOAT;

    -- Calcula el promedio de las calificaciones para el docente especificado
    SELECT AVG(calificacion) INTO promedio
    FROM respuestas_encuesta
    WHERE id_docente = docente_id;

    RETURN promedio;
END //

DELIMITER ;

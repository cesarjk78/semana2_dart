# semana2_dart

class Alumno {
  String codigo;
  String nombre;
  late double nota1;
  late double nota2;
  late double nota3;

  // Constructor 1: código y nombre
  Alumno(this.codigo, this.nombre);

  // Constructor 2: notas
  Alumno.conNotas(this.nota1, this.nota2, this.nota3)
      : codigo = '', nombre = ''; // Se asignan valores predeterminados a código y nombre

  // Método toString() para imprimir los datos del alumno
  @override
  String toString() {
    return 'Nombre: $nombre\nCódigo: $codigo\nNotas: $nota1, $nota2, $nota3';
  }

  double calcularPromedio() {
    List<double> notas = [nota1, nota2, nota3];
    notas.sort();

    double promedio = (notas[1] + notas[2]) / 2;
    return promedio;
  }
}

void main() {
  Alumno a1 = Alumno('123', 'Pomni digital circus');
  a1.nota1 = 8.5;
  a1.nota2 = 9.0;
  a1.nota3 = 7.0;

  Alumno a2 = Alumno.conNotas(10.0, 9.0, 6.0);
  a2.codigo = '456';
  a2.nombre = 'El michi michi';

  // Imprimir los datos de los alumnos
  print(a1.toString());
  print('Promedio (sin la menor nota): ${a1.calcularPromedio()}\n');

  print(a2.toString());
  print('Promedio (sin la menor nota): ${a2.calcularPromedio()}');
}

FPDF for use with Symfony2
==========================

Uses FPDF 1.7, tested in Symfony 2.5+

[![Build Status](https://travis-ci.org/FTwex/fpdf-symfony2.svg?branch=master)](https://travis-ci.org/FTwex/fpdf-symfony2)
[![Latest Stable Version](https://poser.pugx.org/ftwex/fpdf-symfony2/v/stable.svg)](https://packagist.org/packages/ftwex/fpdf-symfony2) [![Total Downloads](https://poser.pugx.org/ftwex/fpdf-symfony2/downloads.svg)](https://packagist.org/packages/ftwex/fpdf-symfony2) [![Latest Unstable Version](https://poser.pugx.org/ftwex/fpdf-symfony2/v/unstable.svg)](https://packagist.org/packages/ftwex/fpdf-symfony2) [![License](https://poser.pugx.org/ftwex/fpdf-symfony2/license.svg)](https://packagist.org/packages/ftwex/fpdf-symfony2)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/ftwex/fpdf-symfony2/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/ftwex/fpdf-symfony2/?branch=master)

## Instalation and Usage

Package available on [Composer](https://packagist.org/packages/ftwex/fpdf-symfony2).

If you're using Composer to manage dependencies, you can use

```sh
composer require ftwex/fpdf-symfony2
```

Usage
-----
```php
class WelcomeController extends Controller
{
    public function indexAction()
    {
        $pdf  = new \FPDF_FPDF();
        $pdi  = new \FPDF_FPDI();

        $pdf->AddPage();
        $pdf->SetFont('Arial','B',16);
        $pdf->Cell(40,10,'Hello World!');
        $pdf->Output();
    }
}

```

FPDF
-----
FPDF is a PHP class which allows to generate PDF files with pure PHP, that is to say without using the PDFlib library. FPDF is a open source project: you may use it for any kind of usage and modify it to suit your needs.

- http://www.fpdf.org/

On the fpdf homepage you will find links to the documentation, forums and so on.

Example
-------

See My Controller:

```php
<?php

namespace Acme\DemoBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;
use Symfony\Component\HttpFoundation\Response;

class WelcomeController extends Controller
{
    public function indexAction()
    {
        $pdf  = new \FPDF_FPDF();
        $pdi  = new \FPDF_FPDI();

        //my code...

        return new Response($pdf->Output( 'MyPDF.pdf', 'I'), 200, array('Content-Type' => 'application/pdf'));
    }
}

```
